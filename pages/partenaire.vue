<template>
    <v-layout
        column
        justify-center
        align-center
    >
    <v-container>
        <v-row>
            <v-col align="center">
               <img src="~/assets/logo_page.png" height="100" alt="">
               <h1> PARTENAIRE </h1>
               <div id="call"> DEVENEZ ENTREPRISE-PARTENAIRE </div>
               <p> Il vous permettra de poster et créer des enqûetes, missions et sondages et de suivre l'avancement de ces tâches , vous pourrez collecter des données validées et filtrées à un prix raisonnable . </p>
            </v-col>
        </v-row>
        <v-row>
            <v-col align="center">
                <h2>
                   Comment ?
                </h2>
                <p>
                    Pour rejoindre notre communauté de entreprises-partenaires, rien de plus simple ! Il suffit de  suivre les étapes suivantes :
                </p>
            </v-col>
        </v-row>
        <v-row>
            <v-col md="6" align="center">
                <v-img
                :src="require('../assets/entreprise_1.jpg')"
                aspect-ratio="1"
                max-height="400"
                >
                </v-img>
            </v-col>
            <v-col md="6" align="center">
                <v-row align="center">
                    <v-spacer></v-spacer>
                    <v-col md="2" align="right">
                        <v-img
                        :src="require('../assets/entreprise_2.png')"
                        class="icon"
                        >
                        </v-img>
                    </v-col>
                    <v-col md="9" align="left">
                        <h2 class="number">
                            +213781872253
                        </h2>
                    </v-col>
                </v-row>
                <h2> Contacter notre admin .</h2>
                <p class="contact"> contactez notre administrateur ,partagez vos informations et coordonnées , et un compte vous sera crée dans notre espace web .</p>
            </v-col>
        </v-row>
        <v-row>
            <v-col align="center">
                <h1 class="fel"> félicitation </h1>
                <p>
                   Vous pouvez se connecter au site web et commencer à visualiser vos tâches et leurs progrés .
                </p>
            </v-col>
        </v-row>
        <v-row>
            <v-col align="right">
                <img src="~/assets/entreprise_3.png" height="700" alt="">
            </v-col>
        </v-row>
       <v-row class="opinions">
           <v-col align="center">
               <p> Si vous avez terminé votre inscription , vous pouvez vous connecter ici :</p>
               <v-btn
               outlined
               color="primary"
               rounded
               x-large
               >
               SE CONNECTER
               </v-btn>
           </v-col>
       </v-row>
        <v-row>
            <flip-component></flip-component>
        </v-row>
    </v-container>
    </v-layout>
</template>

<script>
import FlipComponent from '@/components/FlipComponent.vue';
    export default {
        data() {
            return {
                components: {
                    FlipComponent,
                },       
            }
        },
    }
</script>

<style scoped>
h1{
    content: "";
    width: 200px;
    display: block;
    border-bottom: 5px solid #00adb5;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
p{
    width: 80%;
    font-size: 32px;
    margin: 20px;
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif ;
}
h2{
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif ; 
    font-size: 32px;
}
.services{
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif ;
    font-size: 24px;
    width: 93%;
}
.opinions{
    background-color: #FAFAFA;
} 
.opinion{
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif ;
    font-size: 16px;
    width: 93%;
}
#call{
    margin-top: 20px;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    font-size: 32px;
}
.number{
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    font-size: 32px;
}
.fel{
    content: "";
    width: 210px;
    display: block;
    border-bottom: 5px solid #00adb5;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-transform: uppercase;  
}
</style>