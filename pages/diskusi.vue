<template>
  <v-container>
    <v-card class="pa-16 my-4">
      <h1>Lakukan Diskusi Sekarang</h1>
      <p>
        masalah adalah sebuah hal menarik yang harus diselesaikan dan karena
        itulah kolom diskusi ini ada harapannya, para mahasiswa dapat melakukan
        diskusi dan saling membantu antar sesama
      </p>
      <v-divider></v-divider>
      <p>selalu ingat untu menjaga kesopanan karena ini adalah ruang publik</p>
    </v-card>

    <div class="my-6">
      <h1>Diskusi Populer</h1>
      <v-divider class="my-4"> </v-divider>
      <v-row class="mb-6">
        <v-col
          md="4"
          sm="6"
          lg="3"
          xl="2"
          cols="12"
          v-for="diskusi in diskusis"
          :key="diskusi"
        >
          <v-card>
            <v-card-title> {{ diskusi.prodi }} </v-card-title>
            <v-card-text> {{ diskusi.keterangan }} </v-card-text>
            <v-btn class="ma-4" :to="diskusi.to"> {{ diskusi.tombol }} </v-btn>
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
      diskusis: [
        {
          prodi: 'Teknik Elektro',
          keterangan: 'belajar tentang prodi elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          prodi: 'DKV',
          keterangan: 'belajar tentang prodi elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          prodi: 'Teknik Informatika',
          keterangan: 'belajar tentang prodi elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          prodi: 'Teknik Pertambangan',
          keterangan: 'belajar tentang prodi elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          prodi: 'Teknik Geomatika',
          keterangan: 'belajar tentang prodi elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
      ],
    }
  },
}
</script>

<style></style>
