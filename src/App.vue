<script>
import Lessons from "@/components/Lessons/Lessons.vue";
import StarRating from "@/components/StarRating.vue";

export default {
  name: "App",
  components: {
    StarRating,
    Lessons,
  },
};
</script>

<template>
  <div :id="$style.app">
    <header></header>

    <main>
      <!--      <Lessons />-->

      <StarRating :rating="3.6" />
    </main>
  </div>
</template>

<style module>
#app {
  border: 2px solid red;
}
</style>
