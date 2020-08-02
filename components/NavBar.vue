<template>
    <div>
    <v-app-bar
      dark
    >
    <v-container>
    <v-row align="center">
        <v-col md="3" align="center">
            <v-row>
              <a href="/">
                 <img src="~/assets/logo_nav.png" height="50" alt="">
              </a>
            </v-row>
        </v-col>
        <v-col md="1" align="center">
           <a class="link" href="/">
               ACCUEIL
           </a>
        </v-col>
        <v-col md="1" align="center">
            <a  class="link" href="/client">
               CLIENT
           </a>      
        </v-col>
        <v-col md="1" align="center">
            <a  class="link" href="/partenaire">
               PARTENAIRE
           </a>
        </v-col>
        <v-col md="1" align="center">
            <a  class="link" href="/faq">
               FAQ
           </a>
        </v-col>
        <v-col md="1.5" align="center">
            <a  class="link" href="/contactus">
               NOUS CONTACTER
           </a>
        </v-col>
        <v-col md="2.5" align="center">
             <v-btn  @mouseenter="style=true" @mouseleave="style=false" :outlined="!style" rounded color="primary" > télécharger l'app </v-btn>
        </v-col>
    </v-row> 
    </v-container>
    </v-app-bar>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                style: false,
            }
        },
    }
</script>

<style scoped>
.link {
  position: relative;
  color:whitesmoke;
  text-decoration: none;
}

.link:hover {
  color: whitesmoke;
}
.link::before {
  content: "";
  position: absolute;
  margin-bottom: -8px;
  width: 100%;
  height: 5px;
  bottom: 0;
  left: 0;
  background-color: #00adb5;
  visibility: hidden;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}
.link:hover::before {
  visibility: visible;
  transform: scaleX(1); 
}
</style>