<template>
  <v-app dark>
    <!---- Navigation Bar --------------->
    <nav-bar></nav-bar>
    <!---- Content ---------------------->
    <v-main >
        <nuxt />
    </v-main>
    <!---- Footer ----------------------->
    <footer-component> </footer-component>   
  </v-app>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterComponent from '@/components/FooterComponent.vue';
export default {
  data () {
    return {
      components: {
        NavBar,
        FooterComponent,
      },
    }
  }
}
</script>
