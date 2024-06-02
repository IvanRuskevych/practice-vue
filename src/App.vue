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
    };
  },

  methods: {
    handleItemClick() {
      console.log("item click");
    },
  },
};
</script>

<template>
  <div :id="$style.app">
    <header>
      <CustomInput v-model="searchText" />
      <h3>{{ searchText }}</h3>
    </header>
    <main>
      <ApartmentsList :items="apartments">
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
