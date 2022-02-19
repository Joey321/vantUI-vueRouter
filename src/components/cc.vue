<template>
  <div class="c">
    <!-- 弹出层 -->
    <van-cell is-link @click="showPopup">展示弹出层</van-cell>
    <van-popup v-model="show" position="bottom" :style="{ height: '30%' }" get-container="body" />
    <!-- 输入框 -->
    <van-field
      v-model="value"
      label="文本"
      placeholder="输入框内容右对齐"
      input-align="right"
      required
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      show: false,
      // 输入框值
      value: '',
    };
  },

  methods: {
    showPopup() {
      this.show = true;
    },
  },
};
</script>
<style scoped>
  .c {
   width: 100%;
   height: 600px;
   background-color: rgb(235, 135, 222);
 }
</style>
