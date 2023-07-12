<script setup>

let url = '';
let shortedURL = '';

// Datos de autenticación de la API de Bitly
const accessToken = 'b60c963a6f3ef72410019d7782758d5a18625283';

// URL que deseas acortar
const longUrl = 'https://vuejs.org/api/sfc-script-setup.html#top-level-await';

// Configuración de la solicitud HTTP
// const config = {
//   headers: {
//     Authorization: `Bearer ${accessToken}`,
//     'Content-Type': 'application/json',
//   },
// };
//
// // Cuerpo de la solicitud HTTP
// const data = {
//   long_url: longUrl,
// };
//
// // Realizar la solicitud POST para acortar la URL
// axios.post('https://api-ssl.bitly.com/v4/shorten', data, config)
//     .then(response => {
//       console.log(response.data.link);
//     })
//     .catch(error => {
//       console.error(error);
//     });


const clickCounter = function (){
  console.log('URL' , url)
  shortedURL = url
  console.log('SHORTED URL', shortedURL)
}

</script>

<template>


  <div class="px-0 col-8 mt-5">

    <!--          Form-->
    <form action="">
      <input
          v-model="url"
          class="form-control form-control-lg rounded-0 shorten-url"
          type="text"
          placeholder="Enter a link to shorten it"
          aria-label=".form-control-lg example">
    </form>

    <!--          Form-->
  </div>
  <div class="px-0 col-4 mt-5">
    <button
        v-on:click="clickCounter"
        class="m-0 btn btn-lg btn-warning rounded-0 shorten-url ">Shorten URL ></button>
  </div>

  <!--        Link shorted-->
  <div class="col-4 px-0 mt-5 pt-5">
    <input
        value=""
        class="form-control form-control-lg rounded-0 shorten-url"
        type="text"
        placeholder=""
        aria-label=".form-control-lg example">
  </div>
  <div class="px-0 col-4 mt-5 pt-5">
    <button class="m-0 btn btn-lg btn-warning rounded-0 shorten-url "><span class="material-symbols-outlined">file_copy</span></button>
  </div>

  <!--        Link shorted-->
</template>

<style scoped>

</style>