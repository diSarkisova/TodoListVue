<template>
  <button class="primary-button">
    <component class="primary-button__icon" v-if="icon" :is="icon"></component>
  </button>
</template>

<script setup>
defineProps( {
  icon: {
    type: Object,
    default: null
  }
  })
</script>

<style scoped>

.primary-button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 16px 15px;
  cursor: pointer;
  transition: border-color 0.25s;
  background-color: #333333;
}

.primary-button__icon {
  width: 25px;
  height: 25px;
}

.primary-button:hover :deep(.primary-button__icon path) {
  fill: white;
}

.primary-button:active :deep(.primary-button__icon path) {
  fill: black;
  transition: fill .2s ease-out;
}
</style>