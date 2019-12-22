<template>
  <div class="left_nav">
    <ul>
      <li>POS</li>
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
export default {}
</script>
<style>
.left_nav {
  color: #fff;
  font-size: 10px;
  height: 100%;
  background-color: #232122;
  float: left;
  width: 66px;
}
.iconfont {
  font-size: 22px;
}
.left_nav ul li {
  text-align: center;
  padding: 15px 10px;
  cursor: pointer;
}
.left_nav ul li:first-child {
  background-color: #409eff;
  height: 36px;
  line-height: 36px;
  font-weight: bold;
  font-size: 24px;
}
.left_nav ul li:hover {
  background: #323232;
}
</style>
