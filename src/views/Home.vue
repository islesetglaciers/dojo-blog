<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{ name }} and I am {{ age }} years old.</p>
    <button @click="handleClick">Click Me!</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    console.log('Setup')

    const p = ref(null)

    let name = 'Mario'
    let age = 30

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'Hello Ninjas !'
    }

    return { name, age, handleClick, p }
  }
}
</script>
