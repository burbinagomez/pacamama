<template>
  <section class="main-slider">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="item in gallery" :key="item.index">
        <div
          class="image-layer"
          :style="`
                background-image: url(${item.url});
              `"
        ></div>
        <div class="image-layer-overlay"></div>
        <!-- /.image-layer -->
        <div class="container">
          <div class="row">
            <div class="col-lg-8">
              <div class="main-slider__content">
                <!-- <p v-html="item.subtitle" />
                <h2 v-html="item.title" /> -->
                <!-- <nuxt-link :to="item.buttonUrl" class="thm-btn">
                  <i class="fas fa-arrow-circle-right"></i>
                  {{ item.buttonLabel }}
                </nuxt-link> -->
                <div class="main-slider__shape-1 zoom-fade">
                  <img src="~images/shapes/main-slider-1-shape-1.png" alt="" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </swiper-slide>
    </swiper>
    <MainSliderCounter />
    <!-- If we need navigation buttons -->
    <div class="swiper-pagination" id="main-slider-pagination"></div>
    <div class="main-slider__nav">
      <div class="swiper-button-prev" id="main-slider__swiper-button-next">
        <i class="icon-right-arrow icon-left-arrow"></i>
      </div>
      <div class="swiper-button-next" id="main-slider__swiper-button-prev">
        <i class="icon-right-arrow"></i>
      </div>
    </div>
  </section>
</template>

<script>
import data from "~/data/data.json";
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
  data() {
    return {
      sliderOneCounter: data.sliderOneCounter,
      swiperOptions: {
        slidesPerView: 1,
        loop: true,
        effect: "fade",
        pagination: {
          el: "#main-slider-pagination",
          type: "bullets",
          clickable: true,
        },
        navigation: {
          nextEl: "#main-slider__swiper-button-next",
          prevEl: "#main-slider__swiper-button-prev",
        },
        autoplay: {
          delay: 5000,
        },
      },
    };
  },
  props:{
    gallery:{
      type: Array
    }
  }
};
</script>
