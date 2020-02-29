<template>
  <div id="app">
    <div>
      <LeftNav></LeftNav>
    </div>
    <div>
      <router-view></router-view>
    </div>
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
  #app {
    display: flex;
  }
  #app > div:first-child {
    min-width: 70px;
  }
  #app > div:last-child {
    width: calc(100%-70px);
  }
</style>
