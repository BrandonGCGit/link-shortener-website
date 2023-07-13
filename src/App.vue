<script setup>


import AnimationShootingStars from "@/components/AnimationShootingStars.vue";
import SvgBGStars from "@/components/svg/SvgBGStars.vue";
import SvgLogo from "@/components/svg/SvgLogo.vue";
import ComponentsForm from "@/components/ComponentsForm.vue";
import BottomSection from "@/components/BottomSection.vue";
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
