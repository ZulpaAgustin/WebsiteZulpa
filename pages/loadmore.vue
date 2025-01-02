<script setup>
import { ref } from "vue";

useHead({
  title: "Guru - Website Sekolah",
});

const supabase = useSupabaseClient();
const teachers = ref([]);
const start = ref(0);
const limit = 3;
const loading = ref(false); 

//Fungsi & Percabangan
const Loadmore = async () => {
  try {
    loading.value = true;
    const { data, error } = await supabase
      .from("guru")
      .select("id, nama, mapel, foto")
      // .order("id", { ascending: true })
      .range(start.value, start.value + limit - 1);

    if (error) throw error;
    teachers.value = [...teachers.value, ...data];
    start.value += limit;
  } catch (err) {
    console.error("Error mengambil data:", err.message);
  } finally {
    loading.value = false;
  }
};

const totalData = ref(0);

const TotalTeachers = async () => {
  try {
    const { count, error } = await supabase
      .from("guru")
      .select("*", { count: "exact" });

    if (error) throw error;
    totalData.value = count;
  } catch (err) {
    console.error("Error mengambil total data:", err.message);
  }
};

// Runtunan
Loadmore();
TotalTeachers();
</script>

<template>
  <div class="utama">
    <div class="page-title">
      <h1 class="judul">Guru/Pendidik</h1>
      <p class="text-muted text-center">Guru-Guru SMKN 4 Tasikmalaya</p>
    </div>

    <!-- Baris untuk kartu dan v-for perulangan -->
    <div class="row justify-content-center g-2">
      <div
        v-for="(teacher, index) in teachers" 
        :key="index"
        class="col-md-4 d-flex justify-content-center align-items-stretch"
      >
        <div class="card" style="width: 16rem;">
          <img :src="teacher.foto" alt="Foto Guru" class="card-img-top" />
          <div class="card-body text-center">
            <h5 class="card-title">{{ teacher.nama }}</h5>
            <p class="card-text">{{ teacher.mapel }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Tombol Load More -->
    <div class="text-center mt-3">
      <button
        class="btn btn-dark"
        @click="Loadmore"
        :disabled="loading"
        v-if="teachers.length < totalData || loading"
      >
        {{ loading ? "Memuat..." : "Muat Lebih Banyak" }}
      </button>
    </div>
  </div>
</template>


<style scoped>
.utama {
  margin-top: 90px;
}

.judul {
  font-size: 2.5rem;
  color: #004080;
}

.page-title {
  text-align: center;
  margin-bottom: 2rem;
}

.page-title h1 {
  font-size: 2.5rem;
  color: #004080;
}

.card {
  margin-bottom: 10px;

}
</style>

