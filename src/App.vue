<template>
  <div id="app">

    <side-bar></side-bar>

    <router-view></router-view>
  </div>
</template>

<script>
import SideBar from '@/components/SideBar'

export default {
  name: 'app',
  components: { SideBar }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
<style src="vue-material/dist/vue-material.css"></style>
