<template>
  <div class="task">
    <div class="task__wrapper">
      <input type="checkbox" class="task__checkbox" v-model="checkboxValue">
      <label for="checkbox"></label>
    </div>
    <textarea class="task-primary-textarea" v-model="textareaValue" :placeholder="placeholder"></textarea>
  </div>
</template>

<!--// ДЗ-->
<!--// Расписать по пунктам что делаем-->
<!--// - как работает множественный v-model-->
<!--// - как происходит мутация множественного v-model-->
<!--// - как работает v-model на компонентах-->
<!--// - по аналогии сделать с description-->
<!--// - избавиться от name в TaskCard, а использовать только props task везде будет task.name-->
<!--// - по хорошему thetextarea компонент переназвать на TheTask-->

<script setup>
import {computed} from "vue";

const props = defineProps({
 description: {
    type: String,
    default:""
  },
  isChecked: {
    type: Boolean,
    default:""
  },
  placeholder: {
    type: String,
    default:""
  }
})

const emit = defineEmits(["isChecked","description"])

const checkboxValue = computed({
  get() {
    return props.isChecked
  },
  set(value) {
    emit("update:isChecked",value)
  }
})

const textareaValue = computed({
  get() {
    return props.description
  },
  set(value) {
    emit("update:description",value)
  }
})


</script>

<style scoped>

.task {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.task__wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.task-primary-textarea {
  border: 1px solid transparent;
  font-size: 18px;
  line-height: 18px;
  font-weight: 400;
  border-radius: 8px;
  padding: 6px 17px;
  background-color: #333333;
  color: #F2F2F2;
  width: 100%;
  box-sizing: border-box;
  resize: none;
  align-content: center;
  outline: 0;
  outline-offset: 0;
}

.task__checkbox {
  position: absolute;
  //z-index: -1;
  //opacity: 0;
  margin: 10px 0 0 7px;
}

.task__checkbox + label {
  position: relative;
  padding: 0 0 0 35px;
  cursor: pointer;
}

.task__checkbox:checked + label:after {
  opacity: 1;
}

</style>