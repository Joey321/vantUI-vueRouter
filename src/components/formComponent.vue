<template>
  <div class="form-component">
    <van-form @submit="onSubmit">
      <!-- Field 输入框 -->
      <!-- 传入：抽取出type、label、placeholder -->
      <!-- 传出：value -->
      <van-field
        v-if="type === 'field'"
        :rules="[{ required: true, message: '请输入内容' }]"
        @blur="handleFieldBlur"
        v-model="value"
        :label="label"
        :placeholder="placeholder"
        input-align="right"
        colon
      />
    
    
      <!-- Form 表单选择器 -->
      <!-- 传入：抽取出type、pickerLabel、pickerPlaceholder、columns -->
      <!-- 传出：pickerValue -->
      <!-- 验证要去掉readonly -->
      <van-field
        v-if="type === 'picker'"
        :rules="[{ required: true, message: '请选择' }]"
        
        clickable
        name="picker"
        :value="pickerValue"
        :label="label"
        :placeholder="placeholder"
        @click="showPicker = true"
      />
    <!-- </van-form> -->
      <van-popup v-model="showPicker" position="bottom" get-container="body">
        <van-picker
          show-toolbar
          :columns="columns"
          @confirm="onConfirm"
          @cancel="showPicker = false"
        />
      </van-popup>
    </van-form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      // Field 输入框
      value: '',
      // Form 表单选择器
      pickerValue: '',
      // columns: ['杭州', '宁波', '温州', '嘉兴', '湖州'],
      showPicker: false,
    };
  },
  props: {
    // Prop: 公共
    // field、picker(default)
    type: {
      type: String,
      default: 'picker'
    },
    // Prop: Field
    label: {
      type: String,
      default: '文本'
    },
    placeholder: {
      type: String,
      default: '输入框内容右对齐'
    },
    // Prop: Picker
    // pickerLabel: {
    //   type: String,
    //   default: '选择器'
    // },
    // pickerPlaceholder: {
    //   type: String,
    //   default: '点击选择城市'
    // },
    columns: {
      type: Array,
      default: () => ['杭州', '宁波', '温州', '嘉兴', '湖州']
    }
    
  },
  methods: {
    // Field 输入框失去焦点 输入值
    handleFieldBlur() {
      console.log('Field 输入框失去焦点:', this.value);
    },
    // Form 表单选择器 选中值
    onConfirm(value) {
      this.showPicker = false;
      this.pickerValue = value;
      console.log('Form 表单选择器选中值:', value);
    },
    onSubmit(values) {
      console.log('验证submit:', values);
    }
  },
};
</script>
<style scoped>
</style>
