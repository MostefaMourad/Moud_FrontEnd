<template>
    <v-layout
        column
        justify-center
        align-center
    >
    <v-card
    light
    width="100%"
    >
    <v-row>
        <v-col md="9">
            <gmap-map :center="center" :map-type-id="mapTypeId" :zoom="10">
                <gmap-marker
                    v-for="(item, index) in markers"
                    :key="index"
                    :position="item.position"
                    @click="center = item.position ;dialog=true"
                />
                </gmap-map>
        </v-col>
        <v-col md="3" style="margin-left:-10px">
            <v-card
            light
            outlined
            >
            <v-card-title>
                <v-toolbar flat dark>
                <v-toolbar-title style="margin-left:70px;">
                        Détails
                        <v-btn icon @click="$router.push('/partner/tache/2')">
                        <v-icon>
                        mdi-chevron-right
                        </v-icon>
                        </v-btn>
                </v-toolbar-title>
                </v-toolbar>
            </v-card-title>
            <v-divider
                class="mx-4"
                :inset="inset"
            ></v-divider>
            <v-card-text>
                <v-col>
                    <v-row align="center">
                        Nom de la tâche
                        <v-spacer></v-spacer>
                        <v-chip
                        class="ma-2"
                        color="primary"
                        >
                        6600 DA
                        </v-chip>
                    </v-row>
                    <v-row>
                        <img src="https://picsum.photos/500/300?image=5" alt="" style="width:95%;">
                    </v-row>
                    <v-row>
                      <p>
                          Harness value; facilitate channels integrate revolutionary generate ecologies rich-clientAPIs wireless feeds bricks-and-clicks B2C, "synergies empower, productize innovative, user-centred engage granular." Tagclouds user-centred recontextualize podcasts--out-of-the-box compelling create value-added collaborative deliverables sexy interactive morph. 
                      </p>
                    </v-row>
                </v-col>
            </v-card-text>
            <v-card-actions>
                <v-dialog class="diag" v-model="dialog" persistent max-width="600px">
                    <template>
                        <v-btn
                        color="primary"
                        disabled
                        hidden
                        >
                        </v-btn>
                    </template>
                    <v-card>
                        <v-card-title>
                        <v-col align="center">
                            Réponses
                        </v-col>
                        </v-card-title>
                        <v-card-text>
                        <v-col align="center">
                        <v-row v-for="quest in questions" :key="quest.id">
                            <v-card
                                outlined
                                width="100%"
                                >
                                <v-row align="center">
                                            <v-col md="10">
                                            <v-card-title class="question">
                                                {{quest.question}}
                                            </v-card-title>
                                            </v-col>
                                            <v-col md="2" >
                                                <v-btn
                                                icon
                                                @click="quest.show = !quest.show"
                                                >
                                                <v-icon>{{ quest.show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                                                </v-btn>
                                            </v-col>
                                            </v-row>
                                            <v-expand-transition >
                                            <div v-show="quest.show">
                                                <v-divider></v-divider>
                                                <v-card-text class="reponse">
                                                    {{quest.reponse}}
                                                </v-card-text>
                                            </div>
                                            </v-expand-transition>
                                        </v-card>
                                        &nbsp;&nbsp;&nbsp;
                                    </v-row>
                                    </v-col>
                                    </v-card-text>
                                    <v-card-actions>
                                    <v-col align="center">
                                        <v-btn color="primary" width="90%" @click="dialog = false">Close</v-btn>
                                    </v-col>
                                    </v-card-actions>
                                </v-card>
                            </v-dialog>
                    </v-card-actions>
            </v-card>
        </v-col>
    </v-row>
    </v-card>
    </v-layout>
</template>

<script>
    export default {
        layout:'entreprise',
        data() {
            return {
                center: { lat: 35.6911100, lng: -0.6416700 },
                mapTypeId: "terrain",
                markers: [
                    { position: { lat: 35.73, lng: -0.75 } },
                    { position: { lat: 35.65, lng: -0.616667 } }
                ],
                inset:false,
                dialog:false,
                questions : [
                {
                    id:1,
                    show:false,
                    question:"Comment faire pour recevoir le paeiment ?",
                    reponse:"attendez votre paeiment dans les 24 H , soir par CCP ou par FLEXY , vous pouvez sélécionner la méthode via l'application mobile",
                },
                {
                    id:2,
                    show:false,
                    question:"question 2 ?",
                    reponse:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,",
                },
                {
                    id:3,
                    show:false,
                    question:"question 3 ?",
                    reponse:"Oui",
                },
                {
                    id:4,
                    show:false,
                    question:"question 4 ?",
                    reponse:"Non",
                },
                ],
                }
        },
    }
</script>

<style scoped>
.vue-map-container {
  height: 600px;
  width:100%;
}
.question{
    color: grey;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    font-size: 16px;
}
.reponse{
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-align: left;
    font-size: 12px;  
}

</style>