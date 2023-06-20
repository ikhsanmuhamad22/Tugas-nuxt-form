<template>
    <section class="m-3">
        <form @submit.prevent="inputData">
        <div class="m-4">
            <h2>Input  Siswa</h2>
        </div>
        <div class="mb-3 row">
        <label for="staticEmail" class="col-sm-2 col-form-label">NIS</label>
        <div class="col-sm-10">
            <input v-model="dataSiswa.nis" type="text" class="form-control" id="inputNis">
        </div>
        </div>
        <div class="mb-3 row">
            <label for="inputPassword" class="col-sm-2 col-form-label">Nama Siswa</label>
            <div class="col-sm-10">
            <input v-model="dataSiswa.nama" type="text" class="form-control" id="inputNama">
            </div>
        </div>
        <div class="mb-3 row ">
            <label for="inputPassword" class="col-sm-2 col-form-label">nilai Siswa</label>
            <div class="col-sm-10">
            <input v-model="dataSiswa.nilai" type="number" class="form-control" id="inputNilai">
            </div>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
        </form>
        <hr>
    </section>
</template>

<script>
    export default{
        props:{
            dataSiswa:{
                type: Object
            }
        },
        methods: {
            inputData() {
                this.dataSiswa.push({
                    nis: this.dataSiswa.nis,
                    nama: this.dataSiswa.nama,
                    nilai: this.dataSiswa.nilai,
                })
                this.dataSiswa.nis = ''
                this.dataSiswa.nama = ''
                this.dataSiswa.nilai = ''
                console.log(this.dataSiswa)
            }
        }
    }
</script>