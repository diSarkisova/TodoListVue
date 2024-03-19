<template>
    <div class="task-card">
        <input :disabled="!isEdit" @keydown.enter="onSave" v-model="value" />
        <button v-if="!isEdit" @click="onEdit">Изменить</button>
        <button v-else @click="onSave">Сохранить</button>
    </div>
</template>

<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
    name: {
        type: String
    }
})
const value = ref(props.name)

const emit = defineEmits(["save"])
function onSave() {
    emit("save", value.value)
    isEdit.value = false
}

const isEdit = ref(false)

function onEdit() {
    isEdit.value = true
}
</script>

<!-- ДЗ на 16.02.24
1. Почитать как работает disabled?
2. Рассказать как работает код с занятия
3. Конспект какие бывают атрибуты.
4. Сделать сортироваку computed тасок. -->



//ДЗ
// Сделать условную отрисовку в зависимости от флага isEdit
// Установить динамический атрибут к элементу input(название disabled атрибута, он блокирует доступ к inputa)
// В зависимости от isEdit показывать ту или иную кнопку с помощью директивы v -if v -else.
<style></style>