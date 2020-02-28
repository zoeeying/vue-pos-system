<template>
  <div id="app">
    <LeftNav></LeftNav>
    <div class="main_content">
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
.main_content {
  height: 100%;
  float: left;
  width: calc(100% - 70px);
}
</style>
