<script setup>
import { defineProps, defineEmits } from "vue";

// Оголошуємо пропси та події
const props = defineProps({
  options: {
    type: Array,
    required: true,
  },
  modelValue: {
    type: String,
    default: "",
  },
});

const emit = defineEmits(["update:modelValue"]);
</script>

<template>
  <select
    class="custom-select"
    :value="modelValue"
    @change="(event) => emit('update:modelValue', event.target.value)"
  >
    <option v-for="option in options" :key="option" :value="option">
      {{ option }}
    </option>
  </select>
</template>

<style scoped lang="scss">
@import "../../assets/scss/variables.scss";

.custom-select {
  box-sizing: border-box;
  padding: 8px 15px;
  min-width: 220px;
  min-height: 44px;
  outline: none;
  cursor: pointer;
  border: 2px solid $main-color;
  background-color: #fff;

  font-family: "Montserrat Medium", sans-serif;
  font-size: 18px;
  line-height: 21px;
}
</style>
