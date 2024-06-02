<script>
import ApartmentsItem from "@/components/apartment/ApartmentItem.vue";
import ApartmentsList from "@/components/apartment/ApartmentsList.vue";
import apartments from "@/components/apartment/apartments.js";

export default {
  name: "App",
  components: { ApartmentsList, ApartmentsItem },

  data() {
    return {
      apartments,
      apartment: {
        id: "12345",
        title: "Apartment 1",
        description:
          "Description: Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, aliquam ea eaque eligendi, enim et ipsa molestias nemo nulla quasi rem repellendus sunt tempore veritatis!",
        price: 12345,
        rating: 4.5,
        location: {
          city: "Kyiv",
        },
        owner: {
          name: "Owner 1",
          phone: "123-456-7890",
          email: "owner@example.com",
        },
      },
    };
  },
};
</script>

<template>
  <div :id="$style.app">
    <header></header>
    <main>
      <ApartmentsList :items="apartments">
        <template v-slot:default>Default slot</template>
        <template v-slot:title>New title </template>
        <template v-slot:description> New description </template>
        <template v-slot:apartment="{ apartment }">
          <ApartmentsItem
            :key="apartment.id"
            :description="apartment.description"
            :price="apartment.price"
            :rating="apartment.rating"
            :imgSrc="apartment.imgUrl"
            class="apartments-list__item"
          />
        </template>
      </ApartmentsList>
    </main>
    <footer></footer>
  </div>
</template>

<style module>
#app {
  font-family: Montserrat, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
