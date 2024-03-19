<template>
    <div class="the__form">
        <form @submit.prevent="doSubmit">
            <input type="submit" value="Это форма для отправки" />
        </form>

        <h1 class="form-title">{{ title }}</h1>
    </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from 'vue';

defineProps({
    title: {
        type: String,
        required: true
    }
})

const emit = defineEmits(["on-form"])
function doSubmit() {
    emit("on-form")
}
</script>

<style>
.form-title {
    font-size: 30px;
}
</style>  
