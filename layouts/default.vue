<template>
  <v-app :dark="setTheme">
    <v-navigation-drawer app v-model="drawer" fixed temporary>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title"> Application </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider> </v-divider>
      <v-list-item>
        <v-switch :label="`Dark Theme`" v-model="goDark"></v-switch>
      </v-list-item>
    </v-navigation-drawer>

    <v-app-bar app dense color="primary" elevate-on-scroll fixed>
      <v-container class="py-0 fill-height">
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

        <v-toolbar-title class="pl-7">Learntera</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn text class="ma-2">
          <v-icon left>mdi-magnify</v-icon>
          Cari Apapun Disini
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-container>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <Nuxt />
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      goDark: true,
      clipped: false,
      drawer: false,
      fixed: false,
      group: null,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Home',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Belajar',
          to: '/belajar',
        },
        {
          icon: 'mdi-view-dashboard',
          title: 'Ujian',
          to: '/ujian',
        },
        {
          icon: 'mdi-image',
          title: 'Diskusi',
          to: '/diskusi',
        },
        {
          icon: 'mdi-help-box',
          title: 'Artikel',
          to: '/artikel',
        },
        {
          icon: 'mdi-help-box',
          title: 'Kontak Tim',
          to: '/kontaktim',
        },
        {
          icon: 'mdi-help-box',
          title: 'Login',
          to: '/login',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
  opts: {
    theme: {
      dark: false,
    },
  },

  computed: {
    setTheme() {
      if (this.goDark == true) {
        this.$vuetify.theme.dark = true
      } else {
        this.$vuetify.theme.dark = false
      }
    },
  },
  watch: {
    group() {
      this.drawer = false
    },
  },
}
</script>
