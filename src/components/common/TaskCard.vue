<template>
    <div class="task-card">
        <TheInput class="task-card__created" :disabled="!isEdit" @keydown.enter="onSave" v-model="value"/>
        <TheButton class="task-card__change" v-if="!isEdit" @click="onEdit" :icon="PenIcon">
        </TheButton>
        <TheButton class="task-card__save" v-else @click="onSave" :icon="SaveIcon" ></TheButton>
      <TheButton class="task-card__delete" @click="onDelete" :icon="BasketIcon"></TheButton>
    </div>
</template>

<script setup>
import { ref, defineProps, defineEmits } from 'vue';
import TheInput from "./TheInput.vue";
import TheButton from "../buttons/TheButton.vue";
import PenIcon from "../icons/PenIcon.vue";
import SaveIcon from "../icons/SaveIcon.vue";
import BasketIcon from "../icons/BasketIcon.vue";

const props = defineProps({
    name: {
        type: String
    }
})
const value = ref(props.name)
const isEdit = ref(false)

const emit = defineEmits(["save", "delete"])
function onSave() {
    emit("save", value.value)
    isEdit.value = false
}
function onEdit() {
  isEdit.value = true
}

function onDelete() {
  emit("delete", value.value)
}

</script>

<style lang="scss">
.task-card {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0;
  background-color: #333333;
  border-radius: 8px;
}
</style>

