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
        <v-list-item v-for="(item, i) in items" :key="i" link :to="item.to">
          <v-list-item-icon>
            <v-icon color="primary">{{ item.icon }}</v-icon>
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

    <v-app-bar app dense elevate-on-scroll fixed>
      <v-container class="py-0 fill-height">
        <v-app-bar-nav-icon
          @click.stop="drawer = !drawer"
          class="hidden-lg-and-up"
        ></v-app-bar-nav-icon>
        <v-btn text link to="/"> Learntera </v-btn>
        <v-spacer></v-spacer>
        <v-btn
          text
          class="hidden-md-and-down"
          v-for="(item, i) in items"
          :key="i"
          link
          :to="item.to"
        >
          {{ item.title }}
        </v-btn>
        <v-btn text class="hidden-sm-and-down" to="/cari">
          <v-icon left>mdi-magnify</v-icon>
          Cari
        </v-btn>
        <v-switch v-model="goDark" class="mb-n5 hidden-md-and-down"></v-switch>
      </v-container>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <Nuxt />
      <div class="my-9"></div>
    </v-main>

    <v-bottom-navigation fixed app color="primary" class="hidden-md-and-up">
      <v-btn v-for="(button, i) in bottom" :key="i" :to="button.link">
        <span> {{ button.kata }} </span>
        <v-icon> {{ button.ikon }} </v-icon>
      </v-btn>
    </v-bottom-navigation>

    <v-footer padless class="hidden-sm-and-down" elevation="10">
      <v-card class="flex" flat>
        <v-card-title>
          <h5>Ikuti Learntera Pada Sosial Media Lainnya</h5>
          <v-spacer></v-spacer>
          <v-btn v-for="(icon, i) in icons" :key="i" class="mx-4" dark icon>
            <v-icon size="24px" color="primary">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-title>
        <v-card-text class="py-2 white--text text-center primary">
          {{ new Date().getFullYear() }} — <strong>Learntera</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      icons: ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'],
      value: 1,
      bottom: [
        {
          ikon: 'mdi-home',
          kata: 'Home',
          link: '/',
        },

        {
          ikon: 'mdi-border-color',
          kata: 'Ujian',
          link: '/ujian',
        },
        {
          ikon: 'mdi-comment',
          kata: 'Diskusi',
          link: '/diskusi',
        },
        {
          ikon: 'mdi-magnify',
          kata: 'Cari',
          link: '/cari',
        },
      ],
      goDark: true,
      clipped: false,
      drawer: false,
      fixed: false,
      group: null,
      items: [
        {
          icon: 'mdi-book-open-blank-variant',
          title: 'Belajar',
          to: '/belajar',
        },
        {
          icon: 'mdi-border-color',
          title: 'Ujian',
          to: '/ujian',
        },
        {
          icon: 'mdi-comment',
          title: 'Diskusi',
          to: '/diskusi',
        },
        {
          icon: 'mdi-format-align-left',
          title: 'Artikel',
          to: '/artikel',
        },
        {
          icon: 'mdi-github',
          title: 'Kontak Tim',
          to: '/kontaktim',
        },
        {
          icon: 'mdi-account-circle',
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
