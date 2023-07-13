<script setup>
import {ref} from "vue";



const props = defineProps({
  groupUrls: ref([]),
  // groupUrls: [],
})

const hola = function (){
  console.log('table props', props.groupUrls)
}
</script>

<template>
  <table v-if="groupUrls.length != 0">
    <tr>
      <th>Long Url</th>
      <th>Shorted Url</th>
    </tr>
    <tr v-for="(url, index) in props.groupUrls" :key="index" ref="props">
      <td>{{index}}</td>
      <td><a :href="url.longUrl">{{url.longUrl}}</a></td>
      <td><a :href="url.shortedUrl"> {{url.shortedUrl}}</a></td>
    </tr>
  </table>
  <button v-on:click="hola">kek</button>
</template>

<style scoped>

.border{
  border: 1px solid;
}

</style>