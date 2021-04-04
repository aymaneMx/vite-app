## Getting started with Vue 3 + Vite

### set up Vite

kolchi kayn f [doc](https://vitejs.dev/guide/#getting-started),  

```shell
$ npm init @vitejs/app
```

### set up Tailwind CSS

see [doc](https://tailwindcss.com/docs/guides/vue-3-vite)

```shell script
$ npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

create config file:

```shell
$ npx tailwindcss init -p
```

include Tailwind in your CSS

```css
/* ./src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Finally, ensure your CSS file is being imported in your ./src/main.js file:

```js
// src/main.js
import { createApp } from 'vue'
import App from './App.vue'
import './index.css'

createApp(App).mount('#app')
```

### Install ESLint & Prettier

```shell
$ npm install --save-dev eslint prettier eslint-plugin-vue eslint-config-prettier
```

create file `.eslintrc.js` and past those configs, if you want, 

```js
module.exports = {
    extends: [
        'plugin:vue/vue3-essential',
        'prettier',
    ],
    rules: {
        // override/add rules settings here, such as:
        'vue/no-unused-vars': 'error',
    },
}
```

create file `.prettierrc.js` with those configs:
```js
module.exports = {
    semi: false,
    tabWidth: 4,
    useTabs: false,
    printWidth: 80,
    endOfLine: 'auto',
    singleQuote: true,
    trailingComma: 'es5',
    bracketSpacing: true,
    arrowParens: 'always',
}
```

### Install Vue Router

- For what! why we need Vue Router?
- Vue Router is the official router for Vue.js. It deeply integrates with Vue.js core to make building Single Page Applications with Vue.js a breeze.
[see](https://router.vuejs.org/) for more...

```shell
npm install vue-router@4
```
Ps: we need version 4 for vue3

[see commit changes](https://github.com/aymaneMx/first-vite-project/commit/30b2bc68daec971a14a3274bdb009d2f49d7f8ca)  

- create `src/router/index.js` file with the following code where we will create the router, initiate it with a component called `Home` linked to the path `/` (yes, we will create the component in the coming steps):
```js
import { createRouter, createWebHistory } from 'vue-router'
import Home from '/src/components/Home.vue'

const routes = [
    {
        path: '/',
        name: 'Home',
        component: Home,
    },
]

const router = createRouter({
    history: createWebHistory(),
    routes,
})

export default router
```
- in `App.vue` replace the `helloworld` component to `<router-view/>`.
- Create a home component eg:
```html
<template>
  <h1>Home!!</h1>
</template>
```
- import the router in `main.js` and use it before the app mounted!
```js
import router from "./router/index"
createApp(App).use(router).mount('#app')
```

### Install Vuex

[What is Vuex?](https://vuex.vuejs.org/)

It's basically a state management library, that you probably won't need it if you're building a simple app.

```shell
$ npm install vuex@next --save
```

see [doc](https://vuex.vuejs.org/guide/#the-simplest-store) for more.