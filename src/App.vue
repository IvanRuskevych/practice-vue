<script>
import ApartmentsItem from "@/components/apartment/ApartmentItem.vue";
import ApartmentsList from "@/components/apartment/ApartmentsList.vue";
import apartments from "@/components/apartment/apartments.js";
import CustomInput from "@/components/shared/CustomInput.vue";

export default {
  name: "App",
  components: { CustomInput, ApartmentsList, ApartmentsItem },

  data() {
    return {
      apartments,
      searchText: "",
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

  methods: {
    handleItemClick() {
      console.log("use $emit() for item click");
    },
  },
};
</script>

<template>
  <div :id="$style.app">
    <header>
      <h2>{{ searchText }}</h2>
      <CustomInput v-model="searchText" />
      <!--      <input type="text" v-model="text" />-->
      <!--      <input-->
      <!--        type="text"-->
      <!--        :value="text"-->
      <!--        @input="(event) => (text = event.target.value)"-->
      <!--      />-->
    </header>
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
            @click="handleItemClick"
          />
        </template>
      </ApartmentsList>
    </main>
    <footer></footer>
  </div>
</template>

<style module>
#app {
  font-family: Roboto, sans-serif;
  font-weight: 500;
  text-align: center;
}
</style>
