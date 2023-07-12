<script setup>


import AnimationShootingStars from "@/components/AnimationShootingStars.vue";
import SvgBGStars from "@/components/svg/SvgBGStars.vue";
import SvgLogo from "@/components/svg/SvgLogo.vue";
import ComponentsForm from "@/components/ComponentsForm.vue";
import BottomSection from "@/components/BottomSection.vue";


// Datos de autenticación de la API de Bitly
// const accessToken = 'b60c963a6f3ef72410019d7782758d5a18625283';

// // URL que deseas acortar
// const longUrl = 'https://vuejs.org/api/sfc-script-setup.html#top-level-await';

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

</script>

<template>
  <main>

    <section class="container">
      <!--      bgStars-->
      <svg-b-g-stars></svg-b-g-stars>
      <!--      bgStars-->

      <!--      Star animation-->
      <animation-shooting-stars></animation-shooting-stars>
      <!--      Star animation-->

      <!--      Logo-->
      <div class="row">
        <div class="col-2 mt-5 mb-5 position-relative">
          <svg-logo></svg-logo>
        </div>
      </div>
      <!--      Logo-->

      <!--      Components Form inputs-->
      <div class="row">
        <components-form></components-form>
      </div>
      <!--      Components Form inputs-->

    </section>

    <!--    Bottom Section-->
    <section class="container-fluid">
      <div class="row">
        <bottom-section></bottom-section>
      </div>
    </section>
    <!--    Bottom Section-->

  </main>

</template>

<style scoped>


</style>
