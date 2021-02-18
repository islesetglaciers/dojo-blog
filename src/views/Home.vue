<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search term : {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      {{ name }}
    </div>
    <button @click="handleClick">Stop Watching</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'Home',
  setup() {
    const names = ref(['Mario', 'Yoshi', 'Luigi', 'Bowser', 'Toad', 'Kirby', 'Peach'])
    const search = ref('')

    const stopWatch = watch(search, () => {
      console.log('Watch function ran')
    })

    const stopWatchEffect = watchEffect(() => {
      console.log('watchEffect function ran')
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    // Stop Watch and WatchEffect
    const handleClick = () => {
      stopWatch()
      stopWatchEffect()
    }

    return { names, search, matchingNames, handleClick }
  }
}
</script>
