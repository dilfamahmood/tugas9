<script>
import FormMurid from './components/FormSiswa.vue';

export default {
  name: 'App',
  components: {
    FormMurid
  },
  data() {
    return {
      daftarSiswa: []
    };
  },
  methods: {
    tambahSiswa(siswa) {
      this.daftarSiswa.push(siswa);
    }
  }
};
</script>

<template>
  <div>
    <h1>Daftar Siswa</h1>
    <FormMurid @tambah-siswa="tambahSiswa" />

    <hr />

    <h2>Daftar Siswa</h2>
    <ul>
      <li v-for="(siswa, index) in daftarSiswa" :key="index">
        {{ siswa.nama }} - {{ siswa.usia }} tahun - {{ siswa.gender }} - Kelas {{ siswa.kelas }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f9;
  color: #000;
}
div {
  width: 100%;
  margin: 0;
  padding: 20px;
  background: #ffffff;
  border-radius: 0;
  box-shadow: none;
  box-sizing: border-box;
}
h1 {
  color: #000;
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 10px;
}
h2 {
  font-size: 1.8rem;
  color: #000;
  margin-top: 20px;
  border-bottom: 2px solid #000;
  padding-bottom: 5px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  background-color: #ecf0f1;
  margin: 10px 0;
  padding: 10px 15px;
  border-radius: 5px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  color: #000;
}

li:nth-child(odd) {
  background-color: #dff9fb;
}
@media screen and (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }
  h2 {
    font-size: 1.5rem;
  }
  li {
    font-size: 0.9rem;
    flex-direction: column;
    align-items: flex-start;
  }
  li span {
    margin: 5px 0;
  }
}
@media screen and (max-width: 480px) {
  h1 {
    font-size: 1.8rem;
  }
  h2 {
    font-size: 1.3rem;
  }
  li {
    font-size: 0.8rem;
  }
}
</style>
