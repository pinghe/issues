<template>
  <q-page class="flex flex-center" style="height: 100%">
    <q-carousel
      v-model="currentSlide"
      arrows
      style="height: 100%"
    >
      <q-carousel-slide
        v-for="n in 7" :key="n"
        style="height: 100%"
      >
        <img src="~assets/quasar-logo-full.svg" class="fit">
      </q-carousel-slide>

      <q-carousel-control
        slot="control-button"
        slot-scope="carousel"
        position="bottom-right"
        :offset="[22, 22]"
      >
        <q-btn
          round dense push
          color="primary"
          :icon="carousel.inFullscreen ? 'fullscreen_exit' : 'fullscreen'"
          @click="carousel.toggleFullscreen()"
        />
      </q-carousel-control>

    </q-carousel>
  </q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      currentSlide: 0
    }
  }
}
</script>
