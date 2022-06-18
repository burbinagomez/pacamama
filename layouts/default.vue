<template>
  <v-app>
    <v-app-bar class="primary"
      :clipped-right="true"
      fixed
      app
    >
    <v-icon ></v-icon>
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
    class="primary"
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
        <v-list-item
        v-if="this.$auth.loggedIn"
          router
          exact
          @click="logout()"
        >
          <v-list-item-action>
            <v-icon>mdi-logout</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Cerrar Sesion</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer
    class="primary"
      padless
    >
    <v-container>
      <v-card
        flat
        tile
        class="primary white--text text-center"
      >
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4 black--text"
            icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>
      </v-card>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-email',
        'mdi-instagram',
      ],
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Inicio',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Quienes Somos',
          to: '/about'
        },
        {
          icon: 'mdi-apps',
          title: 'Directorio de Huertas',
          to: '/huertas'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Perfil',
          to: '/perfil'
        },
        {
          icon: 'mdi-apps',
          title: 'Calendario de eventos',
          to: '/anuncios'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Enlaces de interes',
          to: '/interes'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  methods: {
        async logout() {
            await this.$auth.logout()
        },
  }
}
</script>
