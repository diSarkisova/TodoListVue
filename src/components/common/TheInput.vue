<template>
  <input type="text" class="primary-input" :value="modelValue" @input="onInput">
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
</script>

<style scoped>
.primary-input {
  border: 1px solid transparent;
  font-size: 18px;
  line-height: 18px;
  font-weight: 400;
  border-radius: 8px;
  padding: 20px;
  background-color: #333333;
  color: #F2F2F2;
  width: 100%;
  box-sizing: border-box;
}
</style>