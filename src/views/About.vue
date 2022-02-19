<template>
<!-- Expense -->
  <div class="about">
    <!-- 按钮 -->
    <div class="btn-wrapper">
      <van-button type="info" block>Add Expense</van-button>
    </div>
    <!-- 滑动单元格 -->
    <van-swipe-cell>
      <van-cell :border="false" title="滑动单元格" value="内容" />
      <template #right>
        <van-button square type="danger" text="删除" />
      </template>
    </van-swipe-cell>
  </div>
</template>
<style scoped>
  .about {
   width: 100%;
   height: 600px;
   background-color: skyblue;
 }
</style>
