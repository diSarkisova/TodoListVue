<template>
  <button class="primary-button">

  </button>

</template>

<script setup>

</script>

<style scoped>

.primary-button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 18px 18px;
  cursor: pointer;
  transition: border-color 0.25s;
  background-color: #1E6F9F;
}

.primary-button:hover {
  transition: background-color .25s ease-out;
  background-color: #1E6F9F;
}

.primary-button:active {
  background-color: #5E60CE;
}

.primary-button svg {
  width: 25px;
  height: 25px;
}

.primary-button:hover path {
  transition: fill .25s ease-out;
  fill: black;
}
</style>