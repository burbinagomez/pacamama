<template>
<v-row>
  <v-col
    v-for="huerta in huertas"
    :key="huerta.id"
  >
    <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      :src="`${huerta.media[0].url}`"
      height="200px"
    ></v-img>

    <v-card-title>
      {{huerta.nombre}}
    </v-card-title>

    <!-- <v-card-subtitle>
      1,000 miles of wonder
    </v-card-subtitle> -->

    <v-card-actions>
      <v-btn
        color="orange lighten-2"
        text
        :to="`huertas/${huerta.id}`"
      >
        Ver Mas
      </v-btn>
    </v-card-actions>
  </v-card>
  </v-col>
</v-row>
</template>
<script>
export default {
  data () {
    return {
      huertas: [],
      error: null
    }
  },
  async mounted () {
      await this.$axios.$get('/huertas').then(response => {
        this.huertas = response
      })
  }
}
</script>