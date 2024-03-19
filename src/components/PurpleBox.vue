<template>
    <div class="purple__box">
        <the-form :title="title" @on-form="changeTitle" />
    </div>
</template>

<script setup>
import { ref } from 'vue';
import TheForm from './TheForm.vue';
const title = ref("Добрый вечер")

function changeTitle() {
    title.value = ("Получилось!")
}

</script>

<style>
.purple__box {
    background-color: purple;
    width: 200px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>



ДЗ
Передать из компонента pirpleBox переменную title в которой будет строка "Добрый вечер"
ПОчитать как работают emit.
Объявить emit с помощью defineEmits , присвоить const emit=defineEmits...
Отправить наверх событие 