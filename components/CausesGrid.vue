<template>
  <section class="causes-one causes-page">
    <div class="container">
      <div class="row">
        <div
          class="col-xl-4 col-lg-6 col-md-6"
          v-for="item in causes"
          :key="item.index"
        >
          <CausesCard
            :title="item.nombre"
            :amount="{}"
            :thumbnail="item.media[0].url"
            :excerpt="item.descripcion"
            :url="`huertas/${item.id}`"
          />
        </div>
        <!-- /.col-xl-4 col-lg-6 col-md-6 -->
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
  <!-- /.causes-one causes-page -->
</template>
<script>
import CausesCard from "~/components/CausesCard";
export default {
  components: {
    CausesCard,
  },
  props: {
    causes: {
      type: Array,
    },
  }
};
</script>
