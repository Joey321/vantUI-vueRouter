<template>
  <div class="a">
    <!-- 单元格 -->
    <van-cell-group>
      <van-cell title="单元格" value="内容" />
      <van-cell title="单元格" value="内容" label="描述信息" />
      <van-cell title="单元格" value="内容" />
      <van-cell title="单元格" value="内容" label="描述信息" />
    </van-cell-group>
  </div>
</template>
<script>
export default {
  name: 'A',
  data() {
    return {
    }
  },
  methods: {
  },
}
</script>
<style scoped>
  .a {
   width: 100%;
   height: 600px;
   background-color: skyblue;
 }
</style>
