<template>
  <div id="app">
    <base-layout />
    <!-- <home/> -->
  </div>
</template>

<script>
import BaseLayout from './pages/Baselayout.vue'
// import Home from './pages/Home.vue'
export default {
  name: 'App',
  components: {
    BaseLayout, 
    // Home
  }
}
</script>

<style>
*{
  margin : 0;
}

</style>
