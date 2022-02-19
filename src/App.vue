<template>
  <div id="app">
    <keep-alive>
      <router-view />
    </keep-alive>
    <Tab></Tab>
  </div>
</template>

<script>
import Tab from './components/Tab.vue'
export default {
  name: 'App',
  components: {
    Tab
  },
  data() {
    return {

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