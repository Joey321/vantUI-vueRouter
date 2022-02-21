<template>
  <van-tabs v-model="active" @click="onClick">
      <van-tab v-for="(item, i) in tabData" :key="i" :title="item.title" v-html="item.content">
        {{item.content}}
        <!-- v-html不能渲染一个组件 -->
      </van-tab>
  </van-tabs>
</template>

<script>
export default {
  components: {
  },
  props: {
    tabData: {
      type: Array,
      default: ()=>
      [
        { title: '标签 1', content: `<h1>This is an 1 tab</h1>`},
        { title: '标签 2', content: `<h1>This is an 2 tab</h1>`},
        { title: '标签 3', content: `<h1>This is an 3 tab</h1>`},
      ]
    }
  },
  data() {
    return {
      active: 0,
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