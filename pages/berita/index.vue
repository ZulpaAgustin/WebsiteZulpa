<script setup>
useHead({
  title: "Berita Utama - Website Sekolah"
})
</script>

<template>
  <div class="utama news-page">
    <h1 class="page-title text-center mb-4">Berita Sekolah</h1>
    <div class="row">
      <!-- Card 1 -->
      <div class="col-md-4">
        <div class="card" style="width: 100%;">
          <img src="/assets/img/guru.jpg" class="card-img-top news-img" alt="Berita 1">
          <div class="card-body">
            <h5 class="card-title">Upacara Peringatan Hari Guru</h5>
            <p class="card-text">
              Upacara Peringatan Hari Guru Nasional Ke-30, dan HUT PGRI Ke-79 Tahun 2024.
"Guru Hebat Indonesia Kuat".
            </p>
            <nuxt-link to="/berita/1/" class="btn btn-primary">Baca Selengkapnya</nuxt-link>
          </div>
        </div>
      </div>
      <!-- Card 2 -->
      <div class="col-md-4">
        <div class="card" style="width: 100%;">
          <img src="/assets/img/zona.jpg" class="card-img-top news-img" alt="Berita 2">
          <div class="card-body">
            <h5 class="card-title">Perencanaan Zona Integritas</h5>
            <p class="card-text">
              Zona Integritas di Satuan Pendidikan Dinas Pendidikan Provinsi Jawa Barat,
Wujudkan Wilayah Bebas dari Korupsi & Birokrasi Bersih dan Melayani.
            </p>
            <nuxt-link to="/berita/2/" class="btn btn-primary">Baca Selengkapnya</nuxt-link>
          </div>
        </div>
      </div>
      <!-- Card 3 -->
      <div class="col-md-4">
        <div class="card" style="width: 100%;">
          <img src="/assets/img/septi.jpg" class="card-img-top news-img" alt="Berita 3">
          <div class="card-body">
            <h5 class="card-title">Skill Competition 2024</h5>
            <p class="card-text">
              Skill Competition 2024 di selenggarakan oleh Safety Riding Center PT Daya Adicipta Motora Bandung.
            </p>
            <nuxt-link to="/berita/3/" class="btn btn-primary">Baca Selengkapnya</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.utama {
  margin-top: 90px;
  margin-bottom: 20px;
}

.page-title {
  font-size: 2.5rem;
  color: #004080;
}

.news-img {
  height: 200px;
  object-fit: cover; 
}

.card {
  margin-bottom: 20px;
}
</style>
