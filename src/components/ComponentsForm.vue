<script setup>
import {onUpdated, ref} from "vue";



//?Variables
let longUrl = '';
const shortedUrl = ref("");

const groupShortedUrls = ref([])

// const groupShortedUrls = []
//?Variables


// !Methods
const clickCutOutLink = function () {

  // Datos de autenticación de la API de Bitly
  const accessToken = 'b60c963a6f3ef72410019d7782758d5a18625283';

  // URL que deseas acortar
  // const longUrl = 'https://vuejs.org/api/sfc-script-setup.html#top-level-await';

  // Configuración de la solicitud HTTP
  const config = {
    headers: {
      Authorization: `Bearer ${accessToken}`,
      'Content-Type': 'application/json',
    },
  };

  // Cuerpo de la solicitud HTTP
  const data = {
    long_url: longUrl,
  };

  // Realizar la solicitud POST para acortar la URL
  axios.post('https://api-ssl.bitly.com/v4/shorten', data, config)
      .then(response => {
        shortedUrl.value = response.data.link

        groupShortedUrls.value.push({
          longUrl: longUrl,
          shortedUrl: shortedUrl.value
        })

        groupShortedUrls.value.reverse()


        if (groupShortedUrls.value.length > 5){
          groupShortedUrls.value.splice(5)
        }
      })
      .catch(error => {
        console.error(error);
      });


}

const clickCopyShortedUrl = function () {
  navigator.clipboard.writeText(shortedUrl.value)
}

// !Methods


</script>

<template>


  <div class="px-0 col-8 mt-5">

    <!--          Form-->
    <form action="">
      <input
          v-model="longUrl"
          aria-label=".form-control-lg example"
          class="form-control form-control-lg rounded-0 shorten-url"
          placeholder="Enter a link to shorten it"
          type="text">
    </form>

    <!--          Form-->
  </div>
  <div class="px-0 col-4 mt-5">
    <button
        class="m-0 btn btn-lg btn-warning rounded-0 shorten-url "
        v-on:click="clickCutOutLink">Shorten URL >
    </button>
  </div>

  <!--        Link shorted-->
  <div class="col-4 px-0 mt-5 pt-5">
    <input
        :value="shortedUrl"
        aria-label=".form-control-lg example"
        class="form-control form-control-lg rounded-0 shorten-url"
        placeholder=""
        type="text">
  </div>
  <div class="px-0 col-4 mt-5 pt-5">
    <button
        class="m-0 btn btn-lg btn-warning rounded-0 shorten-url "
        v-on:click="clickCopyShortedUrl">
      <span
          class="material-symbols-outlined">
        file_copy
      </span>
    </button>
  </div>

  <!--      Table All URLS-->

  <div class="p-0 mt-5">
    <table class="">
      <thead>
      <tr class="fs-3">
        <th class="pe-5" scope="col">Long Url</th>
        <th scope="col">Shorted Url</th>
      </tr>
      </thead>
      <tbody>
      <tr class="" v-for="url in groupShortedUrls">
        <td class="pe-5"><a class="fs-4 text-decoration-none text-white" :href="url.longUrl">{{url.longUrl}}</a></td>
        <td><a class=" fs-4 text-decoration-none text-warning" :href="url.shortedUrl"> {{url.shortedUrl}}</a></td>
      </tr>
      </tbody>
    </table>
  </div>
  <!--      Table All URLS-->


  <!--        Link shorted-->
</template>

<style scoped>

</style>