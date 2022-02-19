<template>
  <div class="tab-wrapper">
    <van-tabbar route>
      <van-tabbar-item replace to="/" icon="home-o">标签1</van-tabbar-item>
      <van-tabbar-item replace to="/about" icon="search">标签2</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
export default {
  name: 'Tab',
  data() {
    return {
      
    }
  }
}
</script>

<style>
 
</style>