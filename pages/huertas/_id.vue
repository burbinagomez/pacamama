<template>
  <v-container>
      <h1 class="text-center">{{huerta.nombre}}</h1>
      <v-card>
          <v-carousel>
                <v-carousel-item
                v-for="(item,i) in huerta.media"
                :key="i"
                :src="item.url"
                reverse-transition="fade-transition"
                transition="fade-transition"
                ></v-carousel-item>
            </v-carousel>
      </v-card>
      <v-divider
      inset
      ></v-divider>
      <v-divider
      inset
      ></v-divider>
      <v-divider
      inset
      ></v-divider>
      <v-card>
      </v-card>
      <p>
          {{huerta.descripcion}}
      </p>
      <v-row>
          <v-col>
              <ul>
                  <li>
                      Direccion: {{huerta.direccion}}
                  </li>
                  <li>
                      Direccion
                  </li>

              </ul>
          </v-col>
      </v-row>
  </v-container>
</template>

<script>
export default {
    data () {
    return {
      huerta: {},
      error: null,
      id: 0
    }
  },
  async mounted () {
      this.id = this.$route.params.id
      await this.$axios.$get('/huertas/'+this.id).then(response => {
        this.huerta = response
        console.log(this.huerta)
      })
  }
}
</script>

<style>

</style>