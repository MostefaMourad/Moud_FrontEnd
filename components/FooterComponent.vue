<template>
  <v-footer
    dark
    padless
    width="100%"
  >
    <v-card
      flat
      tile
      dark
      width="100%"
      class="white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-text> 
      <v-card-text class="white--text pt-0">
          <v-container>
              <v-row class="container-fluid text-center text-md-left">
                <v-col class="col-md-3 mt-md-0 mt-3">
                    <img src="~/assets/logo_footer.png" class="image" height="150" alt="">
                </v-col>
                <hr class="clearfix w-100 d-md-none pb-3">
                <v-col class="col-md-3 mb-md-0 mb-3">
                    <h3 class="text-uppercase">SERVICE CLIENT</h3>
                    <ul class="list-unstyled">
                    <li v-for="item in items" :key="item.id">
                        <a :href="item.link"> {{item.titre}}</a>
                    </li>
                    </ul>
                </v-col>
                <v-col class="col-md-3 mb-md-0 mb-3">
                    <!-- Links -->
                    <h3 class="text-uppercase">PARTENAIRE MOUD</h3>

                    <ul class="list-unstyled">
                    <li v-for="item1 in items1" :key="item1.id">
                        <a :href="item1.link"> {{item1.titre}}</a>
                    </li>
                    </ul>
                </v-col>
                <v-col class="col-md-3 mb-md-0 mb-3">
                    <!-- Links -->
                    <h3 class="text-uppercase">CONTACTEZ-NOUS</h3>
                    <ul class="list-unstyled">
                    <li>
                        <a href=""> Contacter-Nous </a>
                    </li>
                    <li>
                        <a href="tel:+213550810307">0550 810 307</a>
                    <li>
                        <a href="mailto:contact@moud.dz">support@moud.com</a>
                    </li>
                    <li>
                        <a href="https://goo.gl/maps/BRKHcB228gjgptFw7"> Local à Oran (sur google maps) </a>
                    </li>
                    </ul>
                </v-col>
              </v-row>
          </v-container>
      </v-card-text>
      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong> MOUD </strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
    export default {
        data() {
            return {
                icons: [
                    'mdi-facebook',
                    'mdi-twitter',
                    'mdi-linkedin',
                    'mdi-instagram',
                    'mdi-youtube',
                ],
                items:[
                    {
                      id:1,
                      titre:"C'est quoi MOUD ?",
                      link:"", 
                    },
                    {
                      id:2,
                      titre:"Questions Fréquentes",
                      link:"", 
                    },
                ],
                items1:[
                    {
                      id:1,
                      titre:"C'est quoi Moud Partenaire ?",
                      link:"", 
                    },
                    {
                      id:2,
                      titre:"Questions Fréquentes",
                      link:"", 
                    },
                ],
            }
        },
    }
</script>

<style scoped>
li > a{
  color: whitesmoke;
  text-decoration: none;
}
li > a:hover{
    text-decoration: underline;
}
.image{
    opacity: 0.7;
    margin-top: -50px;
}
</style>