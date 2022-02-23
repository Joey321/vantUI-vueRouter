<template>
<!-- Report -->
  <div class="home">
    <!-- 按钮 -->
    <div class="btn-wrapper">
      <van-button type="info" block @click="showPopup">Add Report</van-button>
    </div>
    <!-- tabs -->
      <van-tabs v-model="active" @click="onClick" animated color="blue">
        <van-tab title="Draft"><A/></van-tab>
        <van-tab title="Pending"><B/></van-tab>
        <van-tab title="All"><C/></van-tab>
      </van-tabs>
    <!-- 组件弹窗 -->
    <van-popup v-model="show">
      <C @closePopup="closePopup"></C>
    </van-popup>
  </div>
</template>
<script>
import A from '../components/a.vue'
import B from '../components/b.vue'
import C from '../components/cc.vue'
export default {
  components: {
    A,
    B,
    C,
  },
  data() {
    return {
      // tabs索引
      active: 0,
      // 组件弹窗
      show: false,
    };
  },
  methods: {
    onClick(name, title) {
      console.log(name, title);
    },
    showPopup() {
      this.show = true;
    },
    closePopup(isShow) {
      this.show = isShow;
    }
  }
};
</script>
<style scoped>
  .home {
   width: 100%;
   height: 600px;
   background-color: #ccc;
 }
 .btn-wrapper {
   width: 100%;
   padding: 5px;
 }
 .van-popup {
   width: 100%;
   height: 100%;
 }
</style>
