<template>
<!-- Report -->
  <div class="home">
    <!-- 按钮 -->
    <div class="btn-wrapper">
      <!-- 点击通过if选择显示 Add Report 组件 数据通过组件传值-->
      <van-button type="info" block @click="showPopup">Add Report</van-button>
    </div>
    <!-- tabs -->
      <van-tabs v-model="active" @click="onClick" animated color="blue">
        <van-tab title="Draft"><A/></van-tab>
        <van-tab title="Pending"><B/></van-tab>
        <van-tab title="All"><C/></van-tab>
      </van-tabs>
    <!-- <Tabbar :tabData="tabData" /> -->
    <van-popup v-model="show">
      <C @closePopup="closePopup"></C>
    </van-popup>
  </div>
</template>
<script>
import A from '../components/a.vue'
import B from '../components/b.vue'
import C from '../components/cc.vue'
// import Tabbar from '../components/Tabbar.vue';
export default {
  components: {
    A,
    B,
    C,  
    // Tabbar,
  },
  data() {
    return {
      active: 0,
      show: false,
      // v-html不能渲染一个组件
      // tabData: [
      //   { title: '标签 1', content: `<A/>`},
      //   { title: '标签 2', content: `<B/>`},
      //   { title: '标签 3', content: `<C/>`},
      // ]
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
