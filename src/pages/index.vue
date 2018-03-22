<template>
  <q-page>
    <q-carousel
      class="absolute-full"
      v-model="currentSlide"
      arrows
    >
      <q-carousel-slide :class="{ 'slide-contain': !!(currentSlide % 2) }"
        v-if="showSlide"
        v-for="n in 7" :key="n"
        img-src="statics/quasar-logo-full.svg"
      >
<!--         <div class="absolute-bottom custom-caption">
          <div class="q-headline">{{ currentSlide % 2 ? 'Contain' : 'Cover'}} Framing</div>
        </div> -->
      </q-carousel-slide>

      <q-carousel-control
        slot="control"
        position="top-right"
        :offset="[hpos, 10]"
        class="text-white"
      >
        <q-btn
          round dense push
          color="primary"
          :icon="showSlide ? 'sync' : 'sync_disabled'"
          @click="toggleShowSlide()"
        />
      </q-carousel-control>

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

<style lang="stylus">
  .slide-contain
    background-size: contain !important;
    background-repeat: no-repeat !important;
  .custom-caption
    text-align center
    padding 12px
    color #ccc
    background rgba(0, 0, 0, 0.5)
</style>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      currentSlide: 0,
      showSlide: true,
      hpos: 10
    }
  },
  methods: {
    toggleShowSlide () {
      this.hpos += 5
      this.showSlide = !this.showSlide
    }
  }
}
</script>
