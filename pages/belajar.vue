<template>
  <v-container>
    <v-card class="my-6">
      <v-row align="center">
        <v-col md="4" sm="5" cols="12">
          <v-img
            class="ma-4"
            :src="require('../assets/img/illust_71911479_20201216_154312.jpg')"
          >
          </v-img>
        </v-col>
        <v-col md="8" sm="7">
          <h2 class="text-center mx-4">
            Tidak Ada Kata Terlambat Untuk Belajar
          </h2>
          <v-card-text>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Vel
            molestias, blanditiis facilis commodi corrupti iusto quasi dolorum
            culpa placeat sapiente ducimus earum delectus architecto laboriosam
            ipsam mollitia accusamus ea aliquam!
          </v-card-text>
        </v-col>
      </v-row>
    </v-card>

    <v-card class="my-10">
      <v-row>
        <v-col md="6" sm="6" cols="12">
          <v-card-title>Tidak Ada Kata Terlambat Untuk Belajar</v-card-title>
          <v-card-text>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Vel
            molestias, blanditiis facilis commodi corrupti iusto quasi dolorum
            culpa placeat sapiente ducimus earum delectus architecto laboriosam
            ipsam mollitia accusamus ea aliquam!
          </v-card-text>
        </v-col>
        <v-col md="6" sm="6" cols="12" class="pa-10">
          <v-text-field
            label="cari matkul atau matkul disini"
            append-outer-icon="mdi-magnify"
          ></v-text-field>
          <v-btn>cari</v-btn>
        </v-col>
      </v-row>
    </v-card>

    <div class="my-6">
      <h1>Mata Kuliah Populer</h1>
      <v-divider class="my-4"> </v-divider>
      <v-row class="mb-6">
        <v-col
          md="4"
          sm="6"
          lg="3"
          xl="2"
          cols="12"
          v-for="(matkul, i) in matkuls"
          :key="i"
        >
          <v-card>
            <v-card-title> {{ matkul.matkul }} </v-card-title>
            <v-card-text> {{ matkul.keterangan }} </v-card-text>
            <v-btn class="ma-4" :to="matkul.to"> {{ matkul.tombol }} </v-btn>
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
      matkuls: [
        {
          matkul: 'Matematika Dasar 1',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Kimia Dasar 1 ',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Fisika Dasar 1',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Pemrograman C++',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Fisika Dasar 2',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
      ],
    }
  },
}
</script>

<style></style>
