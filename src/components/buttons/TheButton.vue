<template>
  <button class="primary-button">
    <component v-if="icon" :is="icon"></component>
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

.primary-button svg {
  width: 25px;
  height: 25px;
}


</style>