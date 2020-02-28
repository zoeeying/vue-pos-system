<template>
  <div id="app">
    <LeftNav></LeftNav>
    <router-view></router-view>
  </div>
</template>

<script>
  import LeftNav from '@/components/LeftNav'
  export default {
    name: 'App',
    components: {
      LeftNav
    }
  }
</script>

<style>
  * {
    box-sizing: border-box;
    padding: 0px;
    margin: 0px;
  }
  html,
  body,
  #app {
    height: 100%;
    font-size: 14px;
  }
  li {
    list-style: none;
  }
</style>
