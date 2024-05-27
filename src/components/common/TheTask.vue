<template>
  <div class="task">
    <div class="task__wrapper">



      <div class="task__checkbox">
        <label class="task__checkbox-label">
          <input type="checkbox" class="task__checkbox-input" v-model="checkboxValue" :checked="toogle" >
        </label>
      </div>



    </div>
<!--      Изначальное:-->
<!--      <input type="checkbox" class="task__checkbox" v-model="checkboxValue">-->
<!--      <label for="checkbox"></label>-->
    <textarea class="task-primary-textarea" v-model="textareaValue" :placeholder="placeholder"></textarea>
  </div>
</template>

<script setup>
import {computed} from "vue";

const props = defineProps({
 description: {
    type: String,
    default:""
  },
  isChecked: {
    type: Boolean,
    default:false
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
.task__checkbox {
  padding: 10px;
}

.task__checkbox-label {
  display: inline-block;
  cursor: pointer;
  position: relative;
  top: 1px;
  left: 0;
  height: 18px;
  width: 18px;
  background-color: transparent;
  border: 2px solid #4EA8DE;
  transition: background-color 0.25s ease;
  border-radius: 50%;
}

.task__checkbox-input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}














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



</style>