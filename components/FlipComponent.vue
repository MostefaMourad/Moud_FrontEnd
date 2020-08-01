<template>
  <v-container>
    <div class="flip-card">
    <div class="flip-card-inner">
        <div class="flip-card-front">
         <v-row align="center">
             <v-col id="child" align="center">
                 BESOIN D'AIDE RANA LAHNA !
             </v-col>
         </v-row>
        </div>
        <div class="flip-card-back">
            <v-container>
            <v-row align="center">
                <v-col align=center>
                    <h1>
                    Nous Restons à votre écoute
                    </h1>
                    <h3>
                        Posez-nous vos questions
                    </h3>
                    <v-btn style="color:whitesmoke;" :to="'/faq'" outlined >
                        Nous Contacter
                    </v-btn>
               </v-col>
            </v-row>               
          </v-container>
        </div>
    </div>
  </div>  
</v-container>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 100%;
  height: 200px;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateX(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: grey;
  color: whitesmoke;
  font-size: 40px;
}

/* Style the back side */
.flip-card-back {
  background-color:#00adb5;
  color: white;
  transform: rotateX(180deg);
}
#child{
    position: absolute;
    top:30%;    
}
h1,h3{
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    margin: 10px;
}
</style>