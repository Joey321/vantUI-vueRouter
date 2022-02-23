<template>
  <div class="b">
  <!-- type: field、picker(default) -->
  <!-- <!-- 传入：type、label、placeholder -->
    <!-- <FormComponent type="field" ref="field1Ref" /> -->
    <!-- <FormComponent type="field" ref="field2Ref" /> -->
  <!-- 传入：type、pickerLabel、pickerPlaceholder、columns -->
    <!-- <FormComponent ref="picker1Ref" /> -->
    <!-- <FormComponent ref="picker2Ref" /> -->

    <div v-for="(item, i) in formDatas" :key="i">
      <FormComponent
        :type="item.type"
        :label="item.label"
        :placeholder="item.placeholder"
        :columns="item.columns"
        :ref="item.ref"
      />
    </div>
  
    <div style="margin: 16px;">
      <van-button block type="info" native-type="submit" @click="requireRef">提交</van-button>
    </div>
  </div>
</template>
<script>
import FormComponent from '../components/formComponent'
export default {
  data() {
    return {
      formDatas: [
        { type: 'field', label: '文本1', placeholder: '输入框内容右对齐1', ref: 'field1Ref' },
        { type: 'field', label: '文本2', placeholder: '输入框内容右对齐2', ref: 'field2Ref' },
        { type: 'picker', label: '选择器1', placeholder: '点击选择城市1', columns: ['杭州1', '宁波1', '温州1', '嘉兴1', '湖州1'], ref: "picker1Ref" },
        { type: 'picker', label: '选择器2', placeholder: '点击选择城市2', columns: ['杭州2', '宁波2', '温州2', '嘉兴2', '湖州2'], ref: "picker2Ref" }
      ]
    };
  },
  components: {
    FormComponent
  },
  methods: {
    // 提交时获取表单子组件Field输入或Picker选中的值
    requireRef() {
      console.log('field1Ref:', this.$refs.field1Ref[0].value);
      console.log('field1Ref:', this.$refs.field1Ref[0].value);
      console.log('field1Ref:', this.$refs.field2Ref[0].value);
      console.log('picker1Ref:', this.$refs.picker1Ref[0].pickerValue);
      console.log('picker2Ref:', this.$refs.picker2Ref[0].pickerValue);
    }
  },
};
</script>
<style scoped>
  .b {
   width: 100%;
   height: 600px;
   background-color: rgb(138, 235, 135);
 }
</style>
