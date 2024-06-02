<script>
import DirectivesTest from "@/components/Lessons/DirectivesTest.vue";
import Button from "@/components/Lessons/Button.vue";

export default {
  name: "Lessons",
  components: {
    DirectivesTest,
    Button,
  },

  data() {
    return {
      amountOfClicks: 0,
    };
  },

  computed: {
    title() {
      return `Amount of clicks: ${this.amountOfClicks}`;
    },
  },

  methods: {
    increment() {
      this.amountOfClicks += 1;
    },
  },
};
</script>

<template>
  <div class="lessons">
    <h1>{{ title }}</h1>
    <Button @click="increment">Click me</Button>
    <Button @click="increment" outlined>Click me outlined</Button>
    <DirectivesTest />
  </div>
</template>

<style scoped>
.lessons {
  color: greenyellow;
  margin-bottom: 60px;
}
</style>
