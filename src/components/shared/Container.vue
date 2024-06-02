<script>
export default {
  name: "Container",
};
</script>

<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<style scoped lang="scss">
.container {
  max-width: 1110px;
  margin: 0 auto;
}
</style>
