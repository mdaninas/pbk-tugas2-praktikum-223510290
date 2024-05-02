    <script setup>
    import { reactive, ref } from 'vue'

    const hitung = ref(0)
    const pesan = reactive('Hello World!')

    const suka = ref(true)

    function ganti() {
      suka.value = !suka.value
    }
    function danger() {
      window.alert("ANDA TELAH DI HACK!!!!!!!!!!1")
    }

    const nama = ref(' ')
    let id = 0
    const program = ref([
      { id: id++, text: 'Python' },
      { id: id++, text: 'Javascript' },
      { id: id++, text: 'C++' }
    ])

    const gaya = ref('gayatext')

    function tambah(){
      hitung.value+=50
    }
    function kurang() {
      hitung.value -= 50
    }
</script>
<template>
  <div class="purple">
    <h2 class="judul">Macam Macam Komponent VUE</h2>
    <div class="red">
      <div class="isi">
        <p class="judul_materi">reactive</p>
        <p>{{ pesan }}</p>
        <p class="judul_materi">ref</p>
        <div class="reactivep">
          <p>{{ hitung }}</p>
          <button @click="tambah">Tambah</button>
          <button @click="kurang">Kurang</button>
        </div>
        <p class="judul_materi">v-bind</p>
        <p :class="gaya">teks ini menggunakan v-bind</p>
        <p class="judul_materi">v-on</p>
        <button @click="danger">JANGAN TEKAN!</button>
        <p class="judul_materi">v-model</p>
        <input type="text" v-model="nama" placeholder="Masukkan Nama Anda">
        <p>Halo : {{ nama }}</p>
        <div class="wrapper2">
          <div class="wrapperif">
            <p class="judul_materi">v-if</p>
            <p v-if="suka">Aku Suka HTML</p>
            <p v-else>Aku Benci C++</p>
            <button @click="ganti">TEKAN UNTUK GANTI NILAI</button>
          </div>
          <p class="judul_materi">v-for </p>
          <div class="list">
            <ul>
              <li v-for="list in program" :key="list.id">
                {{ list.text }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
