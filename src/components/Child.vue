<template>
  <div class="child">
    <button @click="changeNum">点我向父组件传值</button>
  </div>
</template>

<script>
  export default {
    name: 'Child',
    methods: {
      changeNum() {
        this.$emit('numChanged', 4869) // 自定义emitChangeNum事件，传值4869
      }
    }
  }
</script>


