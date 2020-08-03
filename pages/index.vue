<template>
  <v-layout
    column
    justify-center
    align-center
  >
  <!---- Images Slider ------------->

  <v-hover v-slot:default="{ hover }">
    <v-carousel
    cycle
    height="700"
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(quote, i) in quotes"
      :key="i"
      :src="file[i]"
    >
        <v-overlay
            v-if="hoverr"
            absolute
            opacity="0"
            style="margin-left:-60%;margin-top:-20%;"
          >
             <v-card
             flat
             light
             style="opacity:0.7;"
             max-width="400"
             >
               <v-card-text>
                 <v-row align="center" class="link">
                   <v-col md="6">
                     <img src="~/assets/accueil_6.png" style="opacity:1.0;" height="100" alt="">
                   </v-col>
                   <v-col md="6" class="qu" style="opacity:1.0;">
                     commencer à gagner de l'argent
                   </v-col>
                 </v-row>
               </v-card-text>
               <v-divider :inset="inset"></v-divider>
               <v-card-text>
                 <v-row align="center" class="link">
                   <v-col md="6">
                     <img src="~/assets/accueil_5.png" style="opacity:1.0;" height="100" alt="">
                   </v-col>
                   <v-col md="6" class="qu" style="opacity:1.0;">
                    accomplissez vos tâches et missions
                   </v-col>
                 </v-row>
               </v-card-text>
             </v-card>
        </v-overlay>
        <v-expand-transition>
          <div
            v-if="hover"
            class="d-flex transition-fast-in-fast-out primary darken-4 v-card--reveal white--text"
            style="height: 40%;"
          >
            <h1 class="textt">
               {{quote}}
            </h1>
          </div>
        </v-expand-transition>
    </v-carousel-item>
  </v-carousel>
  </v-hover>
  <!---- Cool Animation ------------>

  </v-layout>
</template>

<script>

export default {
  components: {
  },
  data() {
    return {
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
        ],
        file:[
          require('../assets/accueil_1.jpg'),
          require('../assets/accueil_2.jpg'),
          require('../assets/accueil_3.jpg'),
          require('../assets/accueil_4.jpg'),
        ],
        quotes:[
          "Inscrivez-vous gratuitement",
          "Chercher et sélectionner des tâches",
          "Atteindre le montant necessaire , en effectuant des tâches",
          "Encaisser",
        ],
        hoverr:true,
        inset:false,
    }
  },
}
</script>
<style scoped>
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: .5;
  position: absolute;
  width: 100%;
}
.textt{
    font-size: 56px;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-align: center;
    width: 90%;
}
.qu{
  font-size: 24px;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  text-transform: uppercase;
  opacity: 1; 
}
.link {
  position: relative;
  text-decoration: none;
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