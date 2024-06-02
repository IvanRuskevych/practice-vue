<script>
export default {
  data() {
    return {
      isVisible: true,
      fruits: ["kiwi", "banana", "apple"],
      cars: {
        audi: {
          color: "red",
        },
        bmw: {
          color: "green",
        },
      },
    };
  },
};
</script>

<template>
  <div v-if="isVisible">
    <h1 v-show="true" class="title">Title Directives</h1>
    <ul>
      <li v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
    </ul>

    <ul>
      <template v-for="fruit in fruits">
        <li :key="fruit" v-if="fruit === `banana`">
          <<{{ fruit }}>>
        </li></template
      >
    </ul>

    <ul>
      <li v-for="car in cars" :key="car.color">{{ car.color }}</li>
    </ul>

    <ul>
      <li v-for="(car, key) in cars" :key="key">
        {{ `${key} => ${car.color}` }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
.title {
  color: red;
}
</style>
