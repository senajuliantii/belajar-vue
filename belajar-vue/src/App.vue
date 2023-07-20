<script setup>
import { ref } from 'vue';

let msg = "Hallo Duniaa";
let headName = "<h1>Nama Saya Candra</h1>"
let number = 7;
let ok = "NO";
let seen = true; // 1 atau 0

// Split Reverse Message
let message = ref("Hai Vue JS");
function balikkanPesan() {
  message.value = message.value.split('').reverse().join('');
}

// pengulangan
let todos = [
  { teks: 'Belajar JavaScript' },
  { teks: 'Belajar Vue' },
  { teks: 'Buat proyek keren' }
]

// Input
let pesan = ref("Hai Vue");
</script>


<template>
  <div>
    <span>{{ msg }}</span> <br>
    <span style="color:red">Ini Warna Merah</span><br>
    <span v-html="headName"></span>
    <button v-bind:disabled="isButtonDisabled">Tombol</button>
    {{ number + 1 }} <br>
    {{ ok ? 'YES' : 'NO' }} <br>
    {{ msg.split('').reverse().join('') }}
    <!-- Direktif -->
    <p v-if="seen">Sekarang Anda bisa melihatku</p>
  </div>

  <!-- Split Button -->
  <p>{{ message }}</p>
  <button v-on:click="balikkanPesan">Balikkan Pesan</button>

  <!-- For -->
  <br> Pengulangan
  <ol>
    <li v-for="todo in todos">
      {{ todo.teks }}
    </li>
  </ol>

  <!-- Input -->
  <p>{{ pesan }}</p>
  <input v-model="pesan">
</template>