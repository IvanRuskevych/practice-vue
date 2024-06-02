<script>
import StarRating from "@/components/StarRating.vue";

export default {
  name: "ApartmentsItem",
  components: {
    StarRating,
  },

  props: {
    description: {
      type: String,
      default: "",
    },
    rating: {
      type: Number,
      default: 0,
    },
    price: {
      type: Number,
      required: true,
    },
    imgSrc: {
      type: String,
      default: "",
    },
  },

  methods: {
    log(idx, event) {
      console.log("log(): ", idx, event);
    },
    handleLinkClick() {
      console.log("facebook clicked");
    },
  },
};
</script>

<template>
  <!--  <div class="apartments-item" @click="log(2, $event)">-->
  <!--  <div class="apartments-item" @click="$emit('click')">-->
  <!--    vue 3: вже не потрібно привязувати через $emit() -->
  <div class="apartments-item">
    <div class="apartments-item__inner">
      <img :src="imgSrc" alt="" class="apartments-item__photo" />
      <div class="apartments-item__content">
        <p class="apartments-item__description">{{ description }}</p>
        <div class="apartments-item__rating">
          <StarRating :rating="rating" />
        </div>
        <div class="apartments-item__price">UAH {{ price }} per night</div>
        <a href="https://facebook.com" @click.prevent.stop="handleLinkClick"
          >FACEBOOK</a
        >
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.apartments-item {
  position: relative;
  //width: 33.333%;
  max-width: 350px;
  padding: 0 15px;
  margin-bottom: 30px; // краще зробити в ApartmentsList через class="apartments-list__item"

  &__inner {
    position: relative;
  }

  &__content {
    position: relative;
    padding: 20px;
    opacity: 0;
    transition: opacity 0.4s;
    background: rgba(#0f1d2d, 0.7);
    min-height: 200px;
    color: #fff;
    text-align: left;
    line-height: 1.4;
    cursor: pointer;
    z-index: 1;

    &:hover {
      opacity: 1;
    }
  }

  &__description {
    margin-bottom: 20px;
    // обмеження тексту по кількості рядків
    // 1.4 - line-height = 22.4 line-height / 16 font-size
    // 3 - кількість бажаних строк
    // calc(1em * 1.4 * 3) - завжди буде показувати 3 рядки з текстом
    height: calc(1em * 1.4 * 5);
    overflow: hidden;
  }

  &__rating {
    margin-bottom: 20px;
  }

  &__price {
    font-size: 20px;
    font-weight: 600;
  }

  &__photo {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  &__link {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
</style>
