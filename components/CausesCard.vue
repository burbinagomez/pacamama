<template>
  <!--Causes Page Single-->
  <div class="causes-one__single">
    <div class="causes-one__img">
      <div class="causes-one__img-box">
        <img :src="`${thumbnail}`" :alt="title" />
        <nuxt-link :to="url">
          <i class="fa fa-plus"></i>
        </nuxt-link>
      </div>
    </div>
    <div class="causes-one__content">
      <h3 class="causes-one__title">
        <nuxt-link :to="url" v-html="title"></nuxt-link>
      </h3>
      <p class="causes-one__text" v-html="excerpt"></p>
    </div>
    <div class="causes-one__progress">
      <div class="causes-one__goals">
        <p>
          <span>${{ amount.raised }}</span> Raised
        </p>
        <p>
          <span>${{ amount.goal }}</span> Goal
        </p>
      </div>
    </div>
  </div>
</template>
<script>
import countTo from "vue-count-to";
import { ObserveVisibility } from "vue-observe-visibility";
export default {
  components: { countTo },
  directives: {
    ObserveVisibility,
  },
  data() {
    return {
      startBar: false,
      startCounter: false,
    };
  },
  props: {
    title: {
      type: String,
    },
    amount: {
      type: Object,
    },
    thumbnail: {
      type: String,
    },
    excerpt: {
      type: String,
    },
    url: {
      type: String,
    },
  },
  methods: {
    getAmountPercent: function (goal, raised) {
      return parseInt((parseInt(raised, 10) / parseInt(goal, 10)) * 100, 10);
    },
    onVisibilityChange(isVisible) {
      if (isVisible) {
        this.startBar = true;
      }
    },
    onVisibilityCountChange(isVisible) {
      if (isVisible) {
        this.startCounter = true;
      }
    },
  },
};
</script>
