<script>
export default {
  name: "StarRating",
  props: {
    rating: {
      type: Number,
      default: 0,
    },

    starLimit: {
      type: Number,
      default: 5,
    },
  },

  computed: {
    ratingWidth() {
      return (this.rating / this.starLimit) * 100;
    },
    ratingWidthStyle() {
      return `width: ${this.ratingWidth}%;`;
    },
  },
};
</script>

<template>
  <div class="star-rating">
    <span
      v-for="index in starLimit"
      :key="index"
      class="star star--outlined"
    ></span>
    <div class="star-rating__colored" :style="ratingWidthStyle">
      <span
        v-for="index in starLimit"
        :key="index"
        class="star star--colored"
      ></span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.star-rating {
  position: relative;
  display: inline-flex;

  &__colored {
    position: absolute;
    display: inline-flex;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    overflow: hidden;
  }
}

.star {
  display: inline-block;
  width: 16px;
  height: 16px;
  margin: 0 3px;
  flex-shrink: 0;

  &--outlined {
    background: url("/img/star-outlined.svg") center no-repeat;
  }

  &--colored {
    background: url("/img/star-yellow.svg") center no-repeat;
  }
}
</style>
