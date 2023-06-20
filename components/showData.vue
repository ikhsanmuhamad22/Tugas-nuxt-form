<template>
    <section class="p-3 mt-5">
        <div class="m-4">
        <h2>Daftar Siswa</h2>
        <p v-if="!dataSiswa.length">Belum ada data siswa</p>
        </div>
        <div class="row">
        <div v-for="(d,index) in dataSiswa" :key="index" class="card m-3 col-3" style="width: 18rem;">
            <ul class="list-group list-group-flush">
            <li class="list-group-item">{{ d.nis }}</li>
            <li class="list-group-item">{{ d.nama }}</li>
            <li class="list-group-item">{{ d.nilai }}</li>
            </ul>
        </div>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        dataSiswa: {
            type: Object
        }
    },
}
</script>