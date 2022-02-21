<template>
<!-- Expense -->
  <div class="about">
    <!-- 按钮 -->
    <div class="btn-wrapper">
      <van-button type="info" block @click="showPopup">Add Expense</van-button>
    </div>
    <!-- 滑动单元格 -->
    <van-swipe-cell>
      <van-cell :border="false" title="滑动单元格" value="内容" />
      <template #right>
        <van-button square type="danger" text="删除" />
      </template>
    </van-swipe-cell>
    <van-popup v-model="show"><B/></van-popup>
  </div>
</template>
<script>
import B from '../components/b.vue'
export default {
  components: {
    B
  },
  data() {
    return {
      show: false
    }
  },
  methods: {
    showPopup() {
      this.show = true;
    }
  }
}
</script>
<style scoped>
  .about {
   width: 100%;
   height: 600px;
   background-color: skyblue;
 }
 /* .van-popup {
   width: 100%;
   height: 100%;
 } */
</style>
