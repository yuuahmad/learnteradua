<template>
  <v-container>
    <v-carousel v-model="model" hide-delimiters>
      <v-carousel-item
        v-for="(item, i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      >
        <v-row class="fill-height saya" align-content="end">
          <v-col class="text-center pb-10">
            <h1>{{ item.utama }}</h1>
            <p class="hidden-sm-and-down">
              {{ item.sampingan }}
            </p>
          </v-col>
        </v-row>
      </v-carousel-item>
    </v-carousel>

    <!-- If using vue-router -->
    <br />
    <h1 class="text-center">Tujuan Learntera</h1>
    <v-row class="py-6">
      <v-col cols="12" md="4" v-for="kartu in kartus" :key="kartu">
        <v-card elevation="2" shaped class="my-2">
          <v-img :src="kartu.gambar" alt="ini gambar saya"></v-img>
          <v-card-title> {{ kartu.utama }} </v-card-title>
          <v-card-subtitle> {{ kartu.subutama }} </v-card-subtitle>
          <v-card-text> {{ kartu.sampingan }} </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-card class="my-6">
      <v-row align="center">
        <v-col md="6" sm="6" cols="12">
          <v-card-title> Bersama Majukan ITERA </v-card-title>
          <v-card-subtitle> Gabung Tim Learntera Sekarang </v-card-subtitle>
          <v-card-text
            >saat ini kami ingin mengembangkan platform ini dengan sangat cepat
            sehingga kami membutuhkan dukungan kalian agar learntera dapat
            berkembang lebih baik lagi.
          </v-card-text>
          <v-card-text
            >dukungan dapat dilakukan dengan membantu melakukan pembuatan konten
            dan materi, mendesain tampilan web, dan mendesain alogaritma web
          </v-card-text>
        </v-col>
        <v-col md="6" sm="6">
          <v-img
            lazy-src="https://picsum.photos/id/11/10/6"
            src="https://picsum.photos/id/11/500/300"
            class="mx-2"
          >
          </v-img>
        </v-col>
      </v-row>
    </v-card>

    <v-row align="center" class="my-6">
      <v-col md="6" sm="6" class="text-center">
        <h1>ini adalh kata utama</h1>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dignissimos
          ut rerum aut velit, eveniet minus architecto labore quis odit aliquam
          impedit dolores eius consectetur praesentium culpa vero cupiditate,
          magni atque.
        </p>
      </v-col>
      <v-col md="6" sm="6" cols="12">
        <v-card>
          <v-card-title> Bersama Majukan ITERA </v-card-title>
          <v-card-text>
            <p>
              saat ini kami ingin mengembangkan platform ini dengan sangat cepat
              sehingga kami membutuhkan dukungan kalian agar learntera dapat
              berkembang lebih baik lagi.
            </p>
            <p>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. At
              facilis in accusamus id temporibus. Modi aut eligendi laboriosam
              cum eveniet, laudantium perspiciatis necessitatibus enim,
              temporibus ullam blanditiis repellendus aliquid dolore?
            </p>
            <p>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. At
              facilis in accusamus id temporibus. Modi aut eligendi laboriosam
              cum eveniet, laudantium perspiciatis necessitatibus enim,
              temporibus ullam blanditiis repellendus aliquid dolore?
            </p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-card class="my-6">
      <v-card-title class="text-center justify-center py-3">
        <h1 class="font-weight-bold display-1">Tentang ITERA</h1>
      </v-card-title>
      <v-tabs v-model="tab" background-color="transparent" grow>
        <v-tab v-for="tabitem in tabitems" :key="tabitem">
          {{ tabitem }}
        </v-tab>
      </v-tabs>
      <v-tabs-items v-model="tab">
        <v-tab-item v-for="tabitem in tabitems" :key="tabitem">
          <v-row align="center">
            <v-col md="6" sm="6">
              <v-card flat>
                <v-card-title>Ini Adlah Judul Saya</v-card-title>
                <v-card-text>{{ lorems }} </v-card-text>
              </v-card>
            </v-col>
            <v-col md="6" sm="6">
              <v-img
                src="https://picsum.photos/id/11/500/300"
                class="ma-3"
              ></v-img>
            </v-col>
          </v-row>
        </v-tab-item>
      </v-tabs-items>
    </v-card>

    <v-row class="my-6">
      <v-col
        md="3"
        sm="3"
        cols="12"
        v-for="parameter in parameters"
        :key="parameter"
        class="text-center"
      >
        <h2>{{ parameter.judul }}</h2>
        <h3>{{ parameter.angka }}</h3>
        <p>
          {{ parameter.keterangan }}
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  data() {
    return {
      parameters: [
        {
          judul: 'Kelas',
          angka: '1000+',
          keterangan:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eius, ipsa?',
        },
        {
          judul: 'Kelas',
          angka: '1000+',
          keterangan:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eius, ipsa?',
        },
        {
          judul: 'Kelas',
          angka: '1000+',
          keterangan:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eius, ipsa?',
        },
        {
          judul: 'Kelas',
          angka: '1000+',
          keterangan:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eius, ipsa?',
        },
      ],
      tab: null,
      tabitems: ['Appetizers', 'Entrees', 'Deserts'],
      kartus: [
        {
          gambar: require('~/assets/img/illust_71911479_20201216_154312.jpg'),
          utama: 'Kata Pertama',
          subutama: 'ini adalah kata subutama saya pada card saya',
          sampingan:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum, similique? Aspernatur reprehenderit fugiat autem magnam cumque dignissimos ea repellat animi unde, fuga inventore in pariatur voluptatem sequi. Rem, magni dignissimos?',
        },
        {
          gambar: require('~/assets/img/85054286_p0.jpg'),
          utama: 'Kata Utama',
          subutama: 'ini adalah kata subutama saya pada card saya',
          sampingan:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum, similique? Aspernatur reprehenderit fugiat autem magnam cumque dignissimos ea repellat animi unde, fuga inventore in pariatur voluptatem sequi. Rem, magni dignissimos?',
        },
        {
          gambar: require('~/assets/img/86700057_p0.jpg'),
          utama: 'Ini Yang Pertama',
          subutama: 'ini adalah kata subutama saya pada card saya',
          sampingan:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum, similique? Aspernatur reprehenderit fugiat autem magnam cumque dignissimos ea repellat animi unde, fuga inventore in pariatur voluptatem sequi. Rem, magni dignissimos?',
        },
      ],
      lorems:
        'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum, similique? Aspernatur reprehenderit fugiat autem magnam cumque dignissimos ea repellat animi unde, fuga inventore in pariatur voluptatem sequi. Rem, magni dignissimos?',
      model: 0,
      items: [
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          utama: 'Selamat Datang Di Learntera',
          sampingan: 'Platform belajar online mahasiswa ITERA dengan gratis',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          utama: 'Belajar Tanpa Biaya',
          sampingan:
            'disini, kalian dapat belajar matakuliah apapun dengan gratis',
        },
        {
          src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          utama: 'Buat Materi Dan Berbagi Ilmu',
          sampingan:
            'selain belajar, kalian juga dapat mengajar. selain mendapat pahala, juga mendapat pemahaman lebih',
        },
      ],
    }
  },
  components: {
    Logo,
    VuetifyLogo,
  },
}
</script>

<style>
.saya {
  background: linear-gradient(
    to bottom,
    rgba(255, 255, 255, 0),
    rgba(34, 22, 31, 0.73)
  );
  background-size: cover;
  background-position: center;
  height: 520px;
}
</style>
