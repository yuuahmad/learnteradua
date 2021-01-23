<template>
  <v-container>
    <!-- If using vue-router -->
    <h1>ini adalah halaman home</h1>
    <h3>selamat datang di learntera versi kedua</h3>
    <p>
      ini adalah versi penyempurnaan dari learntera versi pertama. dan tampilan
      yang ada pada learntera versi pertama akan saya tempelkan pada learntera
      versi kedua ini.
    </p>
    <p>keunggulan dari versi kedua ini diantaranya adalah</p>
    <p>
      lebih hemat kuota karena resourcenya yang lebih sedikit dibandingkan
      pendahulunya
    </p>
    <p>lebih cepat terload browser</p>
    <p>tampilannya lebih menarik</p>
    <p>proses developnya lebih cepat</p>
    <br /><br /><br />
    <p v-for="lorem in 5" :key="lorem">
      {{ lorems }}
    </p>
  </v-container>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  data() {
    return {
      lorems:
        'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum, similique? Aspernatur reprehenderit fugiat autem magnam cumque dignissimos ea repellat animi unde, fuga inventore in pariatur voluptatem sequi. Rem, magni dignissimos?',
    }
  },
  components: {
    Logo,
    VuetifyLogo,
  },
}
</script>
