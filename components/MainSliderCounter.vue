<template>
  <div class="main-slider__counter">
    <ul class="main-slider__counter-box list-unstyled">
      <li
        v-for="count in sliderOneCounter"
        :key="count.index"
        v-observe-visibility="onVisibilityCountChange"
      >
        <h3 class="main-sldier__counter-digit">
          <countTo
            :startVal="0"
            :endVal="startCounter ? count.count : 0"
            :duration="3000"
            separator=""
          ></countTo>
        </h3>
        <span class="main-slider__counter-text">{{ count.text }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
import countTo from "vue-count-to";
import { ObserveVisibility } from "vue-observe-visibility";
import data from "~/data/data.json";
export default {
  components: { countTo },
  directives: {
    ObserveVisibility,
  },
  data() {
    return {
      startCounter: false,
      sliderOneCounter: data.sliderOneCounter,
    };
  },
  methods: {
    onVisibilityCountChange(isVisible) {
      if (isVisible) {
        this.startCounter = true;
      }
    },
  },
};
</script>
