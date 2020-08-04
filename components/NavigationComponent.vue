<template>
    <div>
    <v-app-bar
      dark
    >
    <v-container>
    <v-row align="center">
        <v-col md="6" align="center">
            <v-row>
              <a href="/MoudFrontEnd/partner/accueil">
                 <img src="~/assets/logo_nav.png" height="50" alt="">
              </a>
            </v-row>
        </v-col>
        <v-sapcer></v-sapcer>
        <v-col md="6" align="right">
             <v-btn color="primary" @click="$router.push('/')"> 
               <v-icon>
                 mdi-logout
               </v-icon>
               se déconnecter
             </v-btn>
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
              
            }
        },
    }
</script>

<style scoped>

</style>