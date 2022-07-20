<template>
  <div>
    <MainSliderOne />
    <!-- <AboutTwo /> -->
    <!-- <CausesCarousel :causes="huertas"/> -->
    <!-- <CallToActionTwo className="" /> -->
    <ThreeBoxes />
    <ContactHome />
    <GalleryCarousel />
    <!-- <TestimonialsCarouselOne className="" /> -->
    <VideoOne />
  </div>
</template>

<script>
export default {
data (){
    return {
      huertas: []
    }
  },
  async mounted(){
    await this.$axios.$get('https://admin.pacamama.com.co/huertas').then(response=>{
      this.huertas = response
    })
  }
};
</script>
