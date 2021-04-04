<template>
  <div class="container px-4 mx-auto">
    <div class="md:flex md:justify-center">
      <div class="md:w-10/12 xl:w-8/12 text-center">
        <h1 class="text-3xl md:text-4xl mb-4">Home :)</h1>
        <div class="mt-6">
          <a
              class="bg-indigo-600 border-2 border-solid border-indigo-600 hover:bg-indigo-700 hover:border-indigo-700 text-white rounded-full py-3 px-8 transition-colors duration-300 mx-2 mt-4">
            <router-link to="/about">About</router-link>
          </a>
          <button
              class="border-2 border-solid border-indigo-600 text-indigo-600 hover:bg-indigo-600 hover:text-white rounded-full py-3 px-8 transition-colors duration-300 mx-2 mt-4"
              @click="incrementCount">
            count is: {{ count }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {computed} from 'vue'
import {useStore} from 'vuex'

const store = useStore()
const count = computed(() => {
      return store.state.count
    }
)

function incrementCount (){
  store.dispatch('incrementAction')
}

</script>