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