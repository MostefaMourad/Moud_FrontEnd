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
               <h1> CLIENT </h1>
               <p> MOUD est un service de tâches innovant qu’on peut utiliser avec son smartphone n’importe où et n’importe quand. Il permet à chacun d'accomplir des taches simples pour le compte de grandes entreprises et d'être rémunéré pour cela . </p>
            </v-col>
        </v-row>
        <v-row>
            <v-col align="right">
                <img src="~/assets/client_1.png" height="650" alt="">
            </v-col>
        </v-row>
        <v-row>
            <v-col align="center">
                <p> Nous avons créé MOUD autour de la conviction que lorsque les gens sont bien traités, ils fournissent un meilleur service. </p>     
            </v-col>
        </v-row>
        <v-row>
            <v-col md="4" align="center">
              <v-img
              :src="require('~/assets/icon_1.png')"
              width="70"
              >
              </v-img>  
             <h2>La simplicité d'usage</h2>
             <p class="services"> Il vous suffit d’un clic pour sélectionner une tâche et commencer à gagner de l'argent .</p>   
            </v-col>
            <v-col md="4" align="center">
              <v-img
              :src="require('~/assets/icon_2.png')"
              width="70"
              >
              </v-img>  
             <h2>La disponibilité</h2>
             <p class="services" >Partout et à tout moment.Vous pouvez vérifier les missions disponibles et gagner de l'argent .</p>   
            </v-col>
            <v-col md="4" align="center">
              <v-img
              :src="require('~/assets/icon_3.png')"
              width="70"
              >
              </v-img>  
             <h2>Au meilleur prix</h2>
             <p class="services">Des tarifs ajustés pour gagner votre fidélité et récompenser vos efforts. </p>   
            </v-col>
        </v-row>
        <v-col class="opinions">
            <v-row>
            <v-col v-for="opinion in opinions" :key="opinion.id" align="left">
                <p class="opinion">
                   {{opinion.opinion}}
                </p>
            </v-col>
            </v-row>
            <v-row>
                <v-col v-for="opinion in opinions" :key="opinion.id" align="left">
                    <v-row>
                    <v-col md="4" align="right">
                        <v-avatar>
                          <img
                            src="https://cdn.vuetifyjs.com/images/john.jpg"
                            alt="John"
                        >
                        </v-avatar>
                    </v-col>
                    <v-col md="8">
                        <h4> {{opinion.user}}</h4>
                        <h5> {{opinion.type}} </h5>
                    </v-col>
                    </v-row>
                </v-col>
            </v-row>
        </v-col>
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
                opinions : [
                    {
                        id:1,
                        opinion:"Juste parfait Ça change les choses premier jour à Alger première fois que j’utilise l’application et franchement c’est superbe rien à dire service parfait bravo et bonne continuation.",
                        user:"Mostefa Mourad",
                        type:"Utilisateur",
                    },
                    {
                        id:2,
                        opinion:"Très bonne prestation service parfait et ponctuelle lors de la réception du paiement , merci et bonne continuation.",
                        user:"Elizabeth murphy",
                        type:"Utilisatrice",
                    },
                    {
                        id:3,
                        opinion:"Application super efficace testée cette semaine à Alger plusieurs fois, rapidité avec le paiement.Je recommande vivement.",
                        user:"Abdelhadi Bouali",
                        type:"Utilisateur",
                    },
                    {
                        id:4,
                        opinion:"On vous donnera quelques question pour répondre parfois prendre des photos ou des mémos , puis en retour , vous gagnerez entre 60 et 200 DA .L'argent facile !",
                        user:"Mohammed douzane",
                        type:"Utilisateur",
                    }
                ],         
            }
        },
    }
</script>

<style scoped>
h1{
    content: "";
    width: 110px;
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

</style>