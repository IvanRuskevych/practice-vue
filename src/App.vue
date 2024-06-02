<script>
import ApartmentsItem from "@/components/apartment/ApartmentItem.vue";
import ApartmentsList from "@/components/apartment/ApartmentsList.vue";
import apartments from "@/components/apartment/apartments.js";
import CustomInput from "@/components/shared/CustomInput.vue";
import CustomSelect from "@/components/shared/CustomSelect.vue";

export default {
  name: "App",
  components: { CustomSelect, CustomInput, ApartmentsList, ApartmentsItem },

  data() {
    return {
      apartments,
      searchText: "",
      selectedOption: "",
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
      <h3>CustomInput: {{ searchText }}</h3>
      <CustomInput v-model="searchText" />

      <h3>CustomSelect: {{ selectedOption }}</h3>
      <CustomSelect
        v-model="selectedOption"
        :options="['value', 'label', 'select']"
      />
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
