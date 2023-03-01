<template>
  <div>
    <MainSliderOne :gallery="gallery.slice(0,5)"/>
    <!-- <AboutTwo /> -->
    <!-- <CausesCarousel :causes="huertas"/> -->
    <!-- <CallToActionTwo className="" /> -->
    <!-- <ThreeBoxes :gallery="gallery.slice(0,2)"/> -->
    <!-- <ContactHome /> -->
    <!-- <GalleryCarousel :gallery="gallery.slice(0,10)"/> -->
    <!-- <TestimonialsCarouselOne className="" /> -->
    <GoogleMap />
    <VideoOne />
  </div>
</template>

<script>
export default {
data (){
    return {
      gallery: []
    }
  },
  async mounted(){
    await this.$axios.$get('https://admin.pacamama.com.co/upload/files').then(response=>{
      this.gallery = response
    })
  }
};
</script>
