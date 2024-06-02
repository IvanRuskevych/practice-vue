<script>
import ApartmentsItem from "./ApartmentItem.vue";
import Container from "@/components/shared/Container.vue";

export default {
  name: "ApartmentsList",
  components: {
    Container,
    ApartmentsItem,
  },

  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<template>
  <Container>
    <div class="apartments-list">
      <ApartmentsItem
        v-for="{ id, description, rating, price, imgUrl } in items"
        :key="id"
        :description="description"
        :price="price"
        :rating="rating"
        :imgSrc="imgUrl"
        class="apartments-list__item"
      /></div
  ></Container>
</template>

<style scoped lang="scss">
.apartments-list {
  display: flex;
  flex-wrap: wrap;
  margin: 0 -15px;

  &__item {
    margin-bottom: 30px;
  }
}
</style>
