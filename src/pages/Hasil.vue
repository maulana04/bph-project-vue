<template>
  <Navbar />
  <div class="flex flex-col justify-center">
    <div class="flex justify-center items-center">
      <TheCard class="w-full">
        <h5 class="text-xl my-4 font-bold text-center">Hasil Deteksi</h5>
        <table class="text-sm">
          <tr>
            <td>Nama</td>
            <td> : Steven</td>
          </tr>
          <tr>
            <td>Usia</td>
            <td> : 57</td>
          </tr>
          <tr>
            <td>Alamat</td>
            <td> : Hongkong</td>
          </tr>
        </table>
        <div class=" mt-3 mx-auto">

          <p class="mt-4 text-center">Anda terindikasi gejala</p>
          <div class="showHasil mt-4 rounded text-white w-1/2 mx-auto text-center"
            :class="{ 'bg-red-500': isRedBackground, 'bg-yellow-400': isYellowBackground, 'bg-green-500': isGreenBackground }">
            {{ textHasil }}
          </div>
        </div>
      </TheCard>
    </div>
    <div class="space-20"></div>
    <Button class="mt-4 mx-auto" @click="backToDashboard">
      OK, back to Dashboard
    </Button>
  </div>
</template>

<style>
.showHasil {
  padding-top: 20px;
  padding-bottom: 20px;
}

.space-80 {
  height: 80px;
}

.space-20 {
  height: 20px;
}
</style>

<script setup>
import Navbar from "../layouts/Navbar.vue";
import { onMounted, ref } from "vue";
import { Input, Button, TheCard } from "flowbite-vue";
import router from "../router";

const isRedBackground = ref(false)
const isYellowBackground = ref(false)
const isGreenBackground = ref(false)
const textHasil = ref('')


onMounted(() => {
  isRedBackground.value = false
  isYellowBackground.value = true
  isGreenBackground.value = false
  textHasil.value = 'Ringan'
});

// function
function backToDashboard() {
  router.push("/");
}
</script>
