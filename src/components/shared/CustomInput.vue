<script setup>
defineProps(["modelValue"]);
defineEmits(["update:modelValue"]);
</script>

<template>
  <input
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    class="custom-input"
  />
</template>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.custom-input {
  padding: 8px 15px;
  min-width: 220px;
  min-height: 44px;
  outline: none;
  border: 2px solid $main-color;
  font-size: 18px;

  font-family: "Montserrat Medium", sans-serif;
  font-size: 18px;
  line-height: 21px;
  //line-height: inherit;
}
</style>
