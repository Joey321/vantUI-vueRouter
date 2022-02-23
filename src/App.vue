<template>
  <div id="app">
  <!-- Tabbar切换组件 -->
    <keep-alive>
      <Home v-if="active === 0" />
      <About v-if="active === 1" />
    </keep-alive>
     <!-- 底部Tabbar -->
    <van-tabbar v-model="active">
      <van-tabbar-item icon="friends-o">标签</van-tabbar-item>
      <van-tabbar-item icon="setting-o">标签</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
import Home from './views/Home'
import About from './views/About'
export default {
  name: 'App',
  components: {
    Home,
    About
  },
  data() {
    return {
      // Tabbar索引
      active: 0,
    }
  },
  methods: {
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>