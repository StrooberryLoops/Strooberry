<script setup>
import {ref, onMounted} from 'vue'

let prayerTimes = ref([])

onMounted(async function(){

  let response = await fetch("https://www.e-solat.gov.my/")
  let data = await response.json()
  prayerTimes.value = data.prayerTime
  console.log(data.prayerTime)
})

</script>

<template>

  <div v-for="time in prayerTimes">
    <p class="text-x1"> {{ time.hijri }} </p>
    <p class="text-x1"> {{ date }} </p>
    <p class="text-x1"> {{ day }} </p>
    <p class="text-x1"> {{ imsak }} </p>
    <p class="text-x1"> {{ fajr }} </p>
    <p class="text-x1"> {{ syuruk }} </p>
    <p class="text-x1"> {{ dhuhr }} </p>
    <p class="text-x1"> {{ asr }} </p>
    <p class="text-x1"> {{ mahgrib }} </p>
    <p class="text-x1"> {{ isha }} </p>

  </div>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
