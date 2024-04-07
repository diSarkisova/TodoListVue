<template>
  <input type="text" class="primary-input" :value="modelValue" @input="onInput">

<!--  <input type="text" class="primary-input" v-model="model"/>-->
</template>

<script setup>
const props = defineProps({
  modelValue: {
    type: String,
    required: true
  }
})
const emit = defineEmits(["update:modelValue"])

function onInput (event) {
  emit('update:modelValue', event.target.value)
}

// import { defineModel } from 'vue';
// const model = defineModel()

</script>

<style scoped>
.primary-input {
  border: 1px solid transparent;
  font-size: 18px;
  line-height: 18px;
  font-weight: 400;
  border-radius: 8px;
  padding: 8px 16px;
  background-color: #333333;
  color: #F2F2F2;
}
</style>