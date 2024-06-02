<script>
import ApartmentsItem from "@/components/apartment/ApartmentItem.vue";

export default {
  name: "App",
  components: { ApartmentsItem },
  data() {
    return {
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
      <ApartmentsItem
        :description="apartment.description"
        :price="apartment.price"
        :rating="apartment.rating"
        imgSrc="https://1.img-dpreview.com/files/p/TS1200x900~sample_galleries/3122460596/1608601223.jpg"
      />
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
