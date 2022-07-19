<template>
  <section class="gallery-page">
    <div class="container">
      <div class="row">
        <div
          class="col-xl-4 col-lg-6 col-md-6"
          v-for="item in gallery"
          :key="item.index"
        >
          <GalleryCard
            :title="item.id"
            :thumbnail="item.url"
          />
        </div>
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
  <!-- /.gallery-page -->
</template>
<script>
import GalleryCard from "~/components/GalleryCard";
export default {
  components: {
    GalleryCard,
  },
  props:{
    gallery:{
      type:Array
    }
  }
};
</script>
