<script setup>
useHead({
  title: "Kontak - Website Sekolah"
})
</script>

<template>
  <div class="utama">
  <div class="contact-container">
    <!-- Bagian kiri: Formulir Kontak -->
    <div class="form-section">
      <h2>Kontak Kami</h2>
      <form>
        <div class="form-group">
          <label for="name">Nama</label>
          <input type="text" id="name" placeholder="Masukkan nama Anda" />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" placeholder="Masukkan email Anda" />
        </div>
        <div class="form-group">
          <label for="message">Pesan</label>
          <textarea id="message" rows="5" placeholder="Tulis pesan Anda di sini"></textarea>
        </div>
        <button type="submit" class="primary-btn">Kirim Pesan</button>
      </form>
    </div>

    <!-- Bagian kanan: Gambar -->
    <div class="image-section">
      <img src="/assets/img/main.jpg" alt="Kontak Kami" />
    </div>
  </div>
</div>
</template>

<style scoped>
.utama {
  margin-top: 90px;
}

.contact-container {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  background-color: #f8f9fa;
}

.form-section {
  flex: 1;
  max-width: 500px;
  padding: 1rem;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.form-section h2 {
  margin-bottom: 1rem;
  color: #004080;
  font-size: 1.8rem;
  text-align: center;
}

.form-group {
  margin-bottom: 1rem;
}

.form-group label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #333;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #004080;
}

.primary-btn {
  display: block;
  width: 100%;
  padding: 0.8rem;
  background-color: #004080;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 1.2rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.primary-btn:hover {
  background-color: #002d66;
}

.image-section {
  flex: 1;
  max-width: 500px;
  text-align: center;
  padding: 1rem;
}

.image-section img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
</style>