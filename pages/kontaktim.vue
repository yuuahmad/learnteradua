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
          md="6"
          sm="6"
          lg="4"
          xl="3"
          cols="12"
          v-for="tim in tims"
          :key="tim"
        >
          <v-card class="pa-6 text-center">
            <v-avatar color="primary" size="150" class="ma-3">
              <img
                :src="require('../assets/img/86700057_p0.jpg')"
                alt="gambar saya"
            /></v-avatar>
            <h2>{{ tim.nama }}</h2>
            <v-divider class="ma-3"></v-divider>
            <p>Prodi : {{ tim.prodi }}</p>
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
          nama: 'Ahmad Yusuf Maulana',
          prodi: 'teknik elektro',
          ttl: 'jepara, 19 juni 2001',
        },
        {
          nama: 'Ahmad Zaini',
          prodi: 'teknik informatika',
          ttl: 'bandung, 2 januari 2001',
        },
        {
          nama: 'Amri',
          prodi: 'farmasi',
          ttl: 'lampung, 23 agustus 2000',
        },
        {
          nama: 'Ahmad Jamil',
          prodi: 'teknik elektro',
          ttl: 'bandung, 2 januari 2001',
        },
        {
          nama: 'Safira Hilyana',
          prodi: 'teknik pertambangan',
          ttl: 'lampung, 23 agustus 2000',
        },
        {
          nama: 'Safina Hilyani',
          prodi: 'DKV',
          ttl: 'jepara, 19 juni 2001',
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
