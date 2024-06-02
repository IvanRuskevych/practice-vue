<script>
export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "button",
    },

    outlined: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<template>
  <button
    v-bind:type="type"
    :class="{ btn: true, 'btn--outline': outlined }"
    style="opacity: 0.5"
  >
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  display: inline-block;
  padding: 8px 15px;
  font-size: 18px;
  font-weight: 500;
  min-width: 200px;
  text-align: center;
  color: #ffffff;
  background: #ff662d;
  cursor: pointer;
  border: 1px solid transparent;

  &--outline {
    background: none;
    border: 3px solid blue;
    color: orangered;
  }
}
</style>
