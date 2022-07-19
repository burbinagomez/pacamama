<template>
  <div class="causes-details__left-bar">
    <div class="causes-details__text-box">
      <h3>{{title}}</h3>
      <p class="causes-details__text-1">
        {{description}}
      </p>
    </div>
    <div class="causes-details__share">
      <div class="causes-details__share-social">
        <a href="#"><i class="fab fa-twitter"></i></a>
        <a href="#"><i class="fab fa-facebook-square"></i></a>  
        <a href="#"><i class="fab fa-instagram"></i></a>
      </div>
    </div>
    <div class="causes-details__img">
      <div class="causes-details__progress">
        <div class="causes-details__goals">
          <p><span>25,270</span> Familias impactadas</p>
          <p><span>30,000</span> Organicos Compostados</p>
        </div>
      </div>
    </div>
    <GalleryGrid :gallery="images"/>
  </div>
</template>
<script>
import GalleryCarousel from './GalleryCarousel.vue';
import GalleryGrid from './GalleryGrid.vue';
export default{
    components: { GalleryCarousel, GalleryGrid },
    props: {
        title: {
            type: String
        },
        description: {
            type: String
        },
        images: {
            type: Array
        },
        socials:{
          type: Object
        },
    },
    
}

</script>