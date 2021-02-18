<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <!-- <p ref="p">My name is {{ name }} and I am {{ age }} years old.</p> -->
    <!-- <button @click="handleClick">Click Me!</button> -->
    <!-- <button @click="age++">Change age</button> -->
    <!-- <input type="text" v-model="name"> -->
    <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update Ninja One</button>
    <h2>Reactive</h2>
    <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update Ninja Two</button>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref, reactive } from 'vue'

export default {
  name: 'Home',
  setup() {
    console.log('Setup')

    // const p = ref(null)

    // const name = ref('Mario')
    // const age = ref(30)

    // const handleClick = () => {
      // console.log(p, p.value)
      // p.value.classList.add('test')
      // p.value.textContent = 'Hello Ninjas !'
      // name.value = 'Luigi'
      // age.value = 28
    // }

    // return { name, age, handleClick, p }

    const ninjaOne = ref({ name: 'Mario', age: 30 })
    const ninjaTwo = reactive({ name: 'Luigi', age: 28 })

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }

    // With reactive we don't need to specify we're trying to access the value
    const updateNinjaTwo = () => {
      ninjaTwo.age = 35
    }

    return {
      ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo
    }
  }
}
</script>
