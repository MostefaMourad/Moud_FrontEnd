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
               <h1> MES TÂCHES </h1>
            </v-col>
        </v-row>
        <v-row>
              <v-card flat>
              <v-tabs
                v-model="active_tabs"
                fixed-tabs
                >
                <v-tabs-slider :class="classs"></v-tabs-slider>
                <v-tab
                    href="#mobile-tabs-5-1"
                    class="error--text"
                    color="error"
                >
                    MISSIONS
                </v-tab>

                <v-tab
                    href="#mobile-tabs-5-2"
                    class="secondary--text"
                    color="secondary"
                >
                    SONDAGES
                </v-tab>

                <v-tab
                    href="#mobile-tabs-5-3"
                    class="primary--text"
                >
                    ENQUÊTES    
                </v-tab>
                </v-tabs>
                <v-tabs-items v-model="active_tabs">
                <v-tab-item
                    v-for="i in 3"
                    :key="i"
                    :value="'mobile-tabs-5-' + i"
                >
                    <v-card flat>
                    <v-card-text>
                    <v-container>
                        <v-row v-for="i in 3" :key="i">
                            <v-col v-for="j in 4" :key="j" md="3" >
                               <tache-component>

                               </tache-component>
                            </v-col>
                        </v-row>
                    </v-container>    
                    </v-card-text>
                    </v-card>
                </v-tab-item>
                </v-tabs-items>
            </v-card>    
            </v-row>
            <v-row>
                <v-col align="center" >
                     <v-btn color="primary">
                         Charger Plus
                     </v-btn>
                </v-col>
            </v-row>
        </v-container>
    </v-layout>
</template>

<script>
import TacheComponent from '@/components/TacheComponent.vue';
    export default {
        layout:'entreprise',
        data() {
            return {
                active_tabs: null,
                clas:"red",
                text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
            }
        },
        components: {
            TacheComponent,
        },
         computed: {
             classs() {
                 if(this.active_tabs==null){
                     return "primary";
                 }
                 else{
                   if(this.active_tabs.localeCompare("mobile-tabs-5-1")==0){
                        return "error";   
                    }
                    else if (this.active_tabs.localeCompare("mobile-tabs-5-2")==0) {
                        return "secondary"; 
                    }
                    else{
                        return "primary"; 
                    }    
                 }
             }
         },
    }
</script>

<style scoped>
h1{
    content: "";
    width: 185px;
    display: block;
    border-bottom: 5px solid #00adb5;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
</style>