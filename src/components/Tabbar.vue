<template>
  <van-tabs v-model="active" @click="onClick">
      <van-tab v-for="(item, i) in tabData" :key="i" :title="item.title">
        <!-- 如何动态通过Props传递的组件渲染插槽 -->
        <slot/>
      </van-tab>
  </van-tabs>
</template>

<script>
import B from './b.vue'
export default {
  components: {
    B
  },
  props: {
    tabData: {
      type: Array,
      default: ()=>
      [
        { title: '标签 1', content: `<template><h1>This is an 1 tab</h1></template>`},
        { title: '标签 2', content: `<template><h1>This is an 2 tab</h1></template>`},
        { title: '标签 3', content: `<template><h1>This is an 3 tab</h1></template>`},
      ]
    }
  },
  data() {
    return {
      active: 1,
    };
  },
  methods: {
    onClick(name, title) {
      console.log(name, title);
      console.log(this.tabData);
    },
  }
};
</script>

<style>

</style>