<template>
  <div id="app">
    <router-view/>
    <main-tab-bar/>
  </div>
</template>

<script>
  import  MainTabbar from 'components/content/MainTabbar/MainTabBar'

export default {
  name: 'App',
  components: {
    MainTabbar
  }
}
</script>

<style>
  @import "./assets/css/base.css";
</style>
