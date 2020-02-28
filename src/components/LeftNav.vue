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
    float: left;
    width: 68px;
    height: 100%;
    text-align: center;
    cursor: pointer;
  }
  .left_nav div:first-child {
    padding: 15px 0px 15px 0px;
    background-color: #efd728;
    color: #303030;
    font-weight: bold;
    font-size: 16px;
  }
  .left_nav ul li {
    padding: 15px 0px;
  }
  .left_nav ul li:hover {
    background-color: #303030;
    color: #efd728;
  }
  .iconfont {
    font-size: 24px;
  }
</style>
