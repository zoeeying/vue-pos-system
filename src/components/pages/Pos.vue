<template>
  <div class="pos">
    <el-row>
      <el-col :span="7" class="pos_order" id="posOrder">
        <el-tabs stretch>
          <el-tab-pane label="点餐">点餐</el-tab-pane>
          <el-tab-pane label="挂单">挂单</el-tab-pane>
          <el-tab-pane label="外卖">外卖</el-tab-pane>
        </el-tabs>
      </el-col>
      <el-col :span="17">
        我是产品栏
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Pos',
  // 生命周期，在所有虚拟DOM加载完成后执行的操作
  mounted () {
    let height = document.body.clientHeight
    document.getElementById('posOrder').style.height = height + 'px'
  }
}
</script>
<style scoped>
.pos_order {
  background-color: #f9fafc;
  padding-top: 5px;
}
</style>
