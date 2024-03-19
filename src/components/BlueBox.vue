<template>
    <div class="blue__box">
        <button @click="setCount" class="primary__button">{{ counter }}</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

let counter = ref(1);

function setCount() {
    counter.value = counter.value + 1
}

</script>

<style>
.blue__box {
    background-color: blue;
    width: 200px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.primary__button {
    display: flex;
    width: 40px;
    height: 40px;
    text-decoration: none;
    background-color: white;
    border-color: black;
    color: black;
    font-size: 15px;
}
</style>