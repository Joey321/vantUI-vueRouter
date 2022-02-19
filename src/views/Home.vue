<template>
<!-- Report -->
  <div class="home">
    <!-- 按钮 -->
    <div class="btn-wrapper">
      <!-- 点击通过if选择显示 Add Report 组件 数据通过组件传值-->
      <van-button type="info" block>Add Report</van-button>
    </div>
    <!-- tabs -->
      <van-tabs v-model="active" @click="onClick" animated color="blue">
        <van-tab title="Draft"><A/></van-tab>
        <van-tab title="Pending"><B/></van-tab>
        <van-tab title="All"><C/></van-tab>
      </van-tabs>
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
    };
  },
  methods: {
    onClick(name, title) {
      console.log(name, title);
    },
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
</style>
