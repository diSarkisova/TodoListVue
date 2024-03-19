<template>
    <div class="red__box">
        <PurpleBox />
        <BlueBox />
    </div>
</template>

<script setup>
import PurpleBox from './PurpleBox.vue';
import BlueBox from './BlueBox.vue';


</script>

<style>
.red__box {
    background-color: red;
    width: 500px;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
