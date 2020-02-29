<template>
  <div class="left_nav">
    <div>收银<br>系统</div>
    <ul>
      <li>
        <i class="icon iconfont icon-12"></i>
        <div>收银</div>
      </li>
      <li>
        <i class="icon iconfont icon-dianpu"></i>
        <div>店铺</div>
      </li>
      <li>
        <i class="icon iconfont icon-hanbao"></i>
        <div>商品</div>
      </li>
      <li>
        <i class="icon iconfont icon-ly_huiyuanka"></i>
        <div>会员</div>
      </li>
      <li>
        <i class="icon iconfont icon-tongji"></i>
        <div>统计</div>
      </li>
      <li>
        <i class="icon iconfont icon-shezhi"></i>
        <div>设置</div>
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    name: 'LeftNav'
  }
</script>

<style scoped>
  .left_nav {
    background-color: #454545;
    color: #ffffff;
    height: 100%;
    text-align: center;
    cursor: pointer;
  }
  .left_nav > div:first-child {
    padding: 15px 0px 15px 0px;
    background-color: #409eff;
    font-weight: bold;
    font-size: 16px;
  }
  .left_nav ul li {
    padding: 15px 0px;
  }
  .left_nav ul li:hover {
    background-color: #303030;
    color: #409eff;
  }
  .iconfont {
    font-size: 24px;
  }
</style>
