<template>
  <div class="container-md w-75 p-5">
    <inputData :dataSiswa="dataSiswa" :inputData="inputData"></inputData>
    <ShowData :dataSiswa="dataSiswa"></ShowData>
    <div>
      <p>Jumlah Siswa : {{ dataSiswa.length }}</p>
      <p>Nilai Rata Rata Siswa Keseluruhan Siswa : {{ avarangeNilai() }}</p>
    </div>

  </div>
</template>
<script>
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import InputData from '@/components/inputData.vue'
  import ShowData from '@/components/showData.vue'

  export default{
    components: {
      InputData,
      ShowData,
    },
    data(){
      return{

        //saya buat data dummy nya supaya gk perlu input buat liat nilai rata-ratanya
        dataSiswa:[
          {
            nis: '111222120015180038',
            nama: 'ikhsan',
            nilai: 90,
          },
          {
            nis: '111222120015180038',
            nama: 'maulana',
            nilai: 84,
          },
          {
            nis: '111222120015180038',
            nama: 'rizal',
            nilai: 67,
          },
          {
            nis: '111222120015180038',
            nama: 'zahra',
            nilai: 78,
          },
          {
            nis: '111222120015180038',
            nama: 'anggi',
            nilai: 67,
          },
          {
            nis: '111222120015180038',
            nama: 'regina',
            nilai: 91,
          },
          {
            nis: '111222120015180038',
            nama: 'rina',
            nilai: 60,
          },
        ]
      }
    },
    methods:{
      avarangeNilai(){
        const nilai = []
        for(let i of this.dataSiswa){
          nilai.push(i.nilai)
        }
        const average = nilai.reduce((a, b) => a + b, 0) / nilai.length
        return Math.round(average)
      }
    }
  }
</script>