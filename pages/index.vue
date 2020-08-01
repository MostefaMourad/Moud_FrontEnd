<template>
  <v-layout
    column
    justify-center
    align-center
  >
  <!---- Images Slider ------------->
    <v-carousel
    cycle
    height="700"
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(slide, i) in slides"
      :key="i"
      :src="items[i].src"
    >
    </v-carousel-item>
  </v-carousel>
  
  <!---- Cool Animation ------------->

  </v-layout>
</template>

<script>

export default {
  components: {
  },
  data() {
    return {
      colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
        ],
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
        ],
        items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          },
        ],
 
    }
  },
}
</script>
