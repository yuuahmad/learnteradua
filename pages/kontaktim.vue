<template>
  <v-container>
    <v-row align="center">
      <v-col md="4" sm="5" cols="12">
        <v-img
          class="ma-4"
          :src="require('../assets/img/illust_71911479_20201216_154312.jpg')"
        >
        </v-img>
      </v-col>
      <v-col md="8" sm="7">
        <h1 class="text-center mx-4">Tim Kami</h1>
        <h3 class="text-center mx-4">
          Kami Adalah Kumpulan Orang Yang Ingin Terus Belajar
        </h3>
        <v-card-text>
          kami, para mahasiswa itera yang ingin melakukan sesuatu terhadap
          lingkungan kami dan orang lain, agar mahasiswa dapat menjadi mahasiswa
          yang sesungguhnya, mahasiswa yang bukanhanya memiliki ijazah, namun
          juga keterampilan.
        </v-card-text>
      </v-col>
    </v-row>

    <div class="my-6">
      <h1>Anggota Tim Learntera</h1>
      <v-divider class="my-4"> </v-divider>
      <v-row class="mb-6">
        <v-col
          sm="6"
          md="4"
          lg="3"
          xl="2"
          cols="12"
          v-for="(tim, i) in tims"
          :key="i"
        >
          <v-card class="pa-6 text-center">
            <img :src="tim.gambar" alt="gambar saya" height="150" />
            <h2>{{ tim.nama }}</h2>
            <v-divider class="ma-3"></v-divider>
            <p>Prodi : {{ tim.prodi }}</p>
            <p>Hobi : {{ tim.hobi }}</p>
            <p>TTL : {{ tim.ttl }}</p>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      tims: [
        {
          gambar: require('~/assets/img/yusuf.jpeg'),
          nama: 'Ahmad Yusuf Maulana',
          prodi: 'Teknik Elektro',
          hobi: 'Programming',
          ttl: '19 Juni 2001',
        },
        {
          gambar: require('~/assets/img/agung.jpg'),
          nama: 'Agung Bagus Sajiwo',
          prodi: 'Teknik Fiska',
          hobi: '',
          ttl: '25 Oktober 2001',
        },
        {
          gambar: require('~/assets/img/barruni.PNG'),
          nama: 'Barruni Heni Febriani',
          prodi: 'Farmasi',
          hobi: 'Nonton Film/Series, Baca Novel',
          ttl: '02 juli 2001',
        },
        {
          gambar: require('~/assets/img/amri.jpg'),
          nama: 'Amri Arif',
          prodi: 'Farmasi',
          hobi: 'Berenang',
          ttl: '26 September 2000',
        },
        {
          gambar: require('~/assets/img/none.png'),
          nama: 'Galuh Ajeng Kartika Budiharto',
          prodi: 'Farmasi',
          hobi: 'Membaca',
          ttl: '19 Februari 2002',
        },
        {
          gambar: require('~/assets/img/none.png'),
          nama: 'Leonardo Fernanda',
          prodi: '',
          hobi: '',
          ttl: '',
        },
        {
          gambar: require('~/assets/img/none.png'),
          nama: 'Ahmad Jamil Al-hazmi',
          prodi: 'Teknik Elektro',
          hobi: '',
          ttl: '',
        },
        {
          gambar: require('~/assets/img/none.png'),
          nama: 'Ahmad Zaini',
          prodi: '',
          hobi: '',
          ttl: '',
        },
        {
          gambar: require('~/assets/img/none.png'),
          nama: 'Zulia Rahmah Fadhillah',
          prodi: '',
          hobi: '',
          ttl: '',
        },
      ],
    }
  },
}
</script>

<style>
.gambarsaya {
  border-radius: 100%;
}
</style>
