<template>
  <section class="causes-one">
    <div class="container">
      <SectionTitle
        subTitle="Latest Causes"
        title="Find the popular cause <br> and donate them"
      />
      <div class="row">
        <div class="col-xl-12">
          <div class="causes-one__carousel">
            <client-only>
              <vue-tiny-slider v-bind="tinySliderOptions">
                <div class="item" v-for="item in causes" :key="item.id">
                  <CausesCard
                    :title="item.nombre"
                    :amount="{}"
                    :thumbnail="item.media[0].url"
                    :excerpt="item.descripcion"
                    :url="`huertas/${item.id}`"
                  />
                </div>
                <!-- /.item -->
              </vue-tiny-slider>
            </client-only>
          </div>
          <!-- /.causes-one__carousel -->
        </div>
        <!-- /.col-xl-12 -->
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
  <!-- /.causes-one causes-page -->
</template>
<script>
import SectionTitle from "~/components/SectionTitle";
import CausesCard from "~/components/CausesCard";
export default {
  components: {
    SectionTitle,
    CausesCard,
  },
  data() {
    return {
      tinySliderOptions: {
        loop: true,
        items: 1,
        mouseDrag: true,
        autoplay: true,
        nav: true,
        navPosition: "bottom",
        controls: false,
        controlsPosition: "bottom",
        controlsText: [
          "<i class='icon-right-arrow left'></i>",
          "<i class='icon-right-arrow'></i>",
        ],
        autoplayButtonOutput: false,
        responsive: {
          0: {
            gutter: 30,
            items: 1,
          },
          768: {
            gutter: 30,
            items: 2,
          },
          992: {
            gutter: 30,
            items: 2,
          },
          1200: {
            gutter: 30,
            items: 3,
          },
        },
      },
    };
  },
  props:{
    causes:{
      type:Array
    } 
  },
};
</script>
