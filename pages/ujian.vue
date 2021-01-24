<template>
  <v-container>
    <v-card class="pa-16 my-4">
      <h1>Sudah Paham Dengan Apa Yang Diajarkan?</h1>
      <p>
        uji kemampuan kalian dengan ujian yang sudah dirancang secara khusus
        untuk mahasiswa itera. ujian ini telah melalui beberapa saringn sehingga
        soal ujian disini tidak berbeda jauh dengan ujian di ITERA yang
        sebenarnya
      </p>
      <p>
        Learntera memiliki banak artikel yang dapat membuka pengetahuan baru
        kalian. karena, disini akan ada artikel seputar itera seperti cerita
        pertama kali ada di itera, cerita pertama kali kenalan dengan teman
        sekamar asrama, dan tulisan informatif lainnya
      </p>
      <v-divider></v-divider>
      <p>bahaya membaca adalah anda makin banyak ilmu</p>
    </v-card>

    <div class="my-6">
      <h1>Pilih Mata Kuliah Untuk Ujian</h1>
      <v-divider class="my-4"> </v-divider>
      <v-row class="mb-6">
        <v-col
          md="4"
          sm="6"
          lg="3"
          cols="12"
          v-for="matkul in matkuls"
          :key="matkul"
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
          matkul: 'PMC',
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
          matkul: 'Fisika Dasar 2',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Matematika dasar 1',
          keterangan: 'belajar tentang matkul elektro disini gan',
          tombol: 'Buka',
          to: '/buka',
        },
        {
          matkul: 'Matematika dasar 1',
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
