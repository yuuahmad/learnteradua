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
      <v-col cols="12" md="4" v-for="(kartu, i) in kartus" :key="i">
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
        <v-col md="6" cols="12">
          <v-card-title>Gabung Tim Learntera Sekarang </v-card-title>
          <v-card-subtitle>kami butuh dukungan kalian</v-card-subtitle>
          <v-card-text>
            <p>
              saat ini kami ingin mengembangkan platform ini dengan sangat cepat
              sehingga kami membutuhkan dukungan kalian agar learntera dapat
              berkembang lebih baik lagi.
            </p>
            <p>
              dukungan dapat dilakukan dengan membantu melakukan pembuatan
              konten dan materi, mendesain tampilan web, dan mendesain
              alogaritma web.
            </p>
            <p>
              atau, kalian juga dapat membantu kami dengan menyampaikan kritik
              dan saran kalian kepada kami. contohnya seperti ketika kalian
              menemukan bug tampilan, atau tidak bisa mengakses pelajaran yang
              ada disini, atau menemukan halaman 404 not found. kami akan segera
              mengatasinya selagi kami masih ada waktu
            </p>
          </v-card-text>
        </v-col>
        <v-col md="6">
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
        <h1>Apa Itu Learntera</h1>
        <p class="px-12">
          apakah kalian penasaran dengan sejarah dan asal usul terciptanya
          learntera dan ingin tahu apa sih yang sebenarnya terjadi dibalik tim
          pengembang learntera? kalian dapat membaca artikel singkatnya
          disamping ini (mode desktop dan tablet) atau dibawah ini (mode
          smartphone)
        </p>
      </v-col>
      <v-col md="6" sm="6" cols="12">
        <v-card>
          <v-card-title> Cerpen Learntera </v-card-title>
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
      <h1 class="display-1 text-center py-3">Tentang ITERA</h1>
      <v-row>
        <v-col xl="1" lg="2" sm="3" cols="12">
          <v-list rounded>
            <v-list-item-group v-model="tab" color="primary">
              <v-list-item v-for="(tabitem, i) in tabitems" :key="i">
                <v-list-item-content>
                  <v-list-item-title v-text="tabitem"></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-col>
        <v-col xl="11" lg="10" sm="9">
          <v-tabs-items v-model="tab">
            <v-tab-item
              v-for="(tabitem, i) in tabitems"
              :key="i"
              class="mx-6 my-2"
            >
              <h2 class="my-2">Ini Adlah Judul Saya</h2>
              <p>{{ lorems }}</p>
            </v-tab-item>
          </v-tabs-items>
        </v-col>
      </v-row>
    </v-card>

    <h1 class="text-center">Fakta Learntera</h1>
    <v-row class="my-6">
      <v-col
        md="3"
        sm="3"
        cols="12"
        v-for="(parameter, i) in parameters"
        :key="i"
        class="text-center"
      >
        <h2>{{ parameter.judul }}</h2>
        <h3 class="display-3">{{ parameter.angka }}</h3>
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
      lorems:
        '    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Asperiores neque, aliquam vero recusandae facere optio atque debitis ipsa itaque delectus ratione molestias laudantium numquam ipsum, dolor quo, enim quasi blanditiis.',
      parameters: [
        {
          judul: 'Matkul',
          angka: '5',
          keterangan:
            'kami telah menyediakan beberapa matkul dari TPB dan prodi kalian dapat langsung belajar matkul tersebut di halaman belajar',
        },
        {
          judul: 'Pengajar',
          angka: '8',
          keterangan:
            'pengajar kami adalah para mahasiswa yang telah tergabung dalam tim learntera. para pengajar learntera adalah mahasiswa biasa yang bisa ditemukan dimana saja. namun, dengan semangat berbagi mereka yang sangat tinggi',
        },
        {
          judul: 'Developer',
          angka: '1',
          keterangan:
            'developer learntera adalah mereka yang selalu melakukan pembuatan dan perawatan website agar website dapat digunakan dengan baik dan tidak ada masalah',
        },
        {
          judul: 'Pengguna',
          angka: '10',
          keterangan:
            'siap menggunakan learntera? segera daftarkan diri kalian dengan menggunakan email itera. pendaftaran tidak dipungut biaya apapun dan data kalian akan aman',
        },
      ],
      tab: 0,
      tabitems: ['Appetizers', 'Entrees', 'Deserts'],
      kartus: [
        {
          gambar: require('~/assets/img/illust_71911479_20201216_154312.jpg'),
          utama: 'Pendidikan Untuk Semua Orang',
          subutama: 'karena menuntut ilmu adalah wajib hukumnya',
          sampingan:
            'kami menyediakan wadah bagi pelajar itera agar mereka dapat belajar degan tanpa melihat latar belakang mereka. dari manapun kamu, berapapun IPK kamu, dan siapapun itu dirimu, kamu berhak mendapatkan pendidikan sama dengan yang lainnya.',
        },
        {
          gambar: require('~/assets/img/85054286_p0.jpg'),
          utama: 'Memanfaatkan Teknologi',
          subutama: 'teknologi yang pesat mendorong keinginan kami',
          sampingan:
            'seperti yang kita ketahui, dunia sekarang berkembang dengan pesatnya. salahsatu faktornya adalah karena adanya internet yang menghubungkan kita semua. selain itu teknologi 5G, revolusi industri 4.0, dan IoT yang semakin mendominasi dan mulai bermunculan, membuat tim learntera berinisiatif membuat platform ini dengan sungguh-sungguh',
        },
        {
          gambar: require('~/assets/img/86700057_p0.jpg'),
          utama: 'Ikut Mendukung Perkuliahan ITERA',
          subutama: 'pemahaman materi adalah kuncinya',
          sampingan:
            'seringkali mahasiswa itera tidak memahami apa yang dikatakan oleh dosen dan mereka malu untuk bertanya kepada dosen mereka. disinilah peran learntera untuk mahasiswa karena, disini mereka bisa belajar dan mengajar satu sama lainnya. harapannya adalah mahasiswa dapat paham materi yang diajarkan oleh sesama mahasiswa lainnya',
        },
      ],
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
