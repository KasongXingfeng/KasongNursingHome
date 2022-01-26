<template>
   <img class = "img-fluid" alt = "Vue logo" src = "../assets/logo.jpg" />
    <h1 class = "display-1 text-bold"> My App </h1>
    <h1 class = "text-gray-soft text-regular"> Greetings to you all. </h1>
    <HelloWorld msg = "Welcome to Your Vue.js App" />
</template>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>

</style>
