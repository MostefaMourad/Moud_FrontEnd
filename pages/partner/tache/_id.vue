<template>
  <v-container>
    <v-card
    elevation="4"
    dark
    >
      <v-data-table
        :headers="headers"
        :items="data"
        sort-by="calories"
        class="elevation-1"
      >
        <template v-slot:top>
          <v-toolbar flat dark>
            <v-toolbar-title>
              <v-btn icon @click="$router.push('/partner/accueil')">
                <v-icon>
                  mdi-arrow-left
                </v-icon>
              </v-btn>
              Nom Tâche
              </v-toolbar-title>
            <v-divider
              class="mx-4"
              inset
              vertical
            ></v-divider>
            <v-spacer></v-spacer>
            <v-btn color="primary" @click="$router.push('/partner/carte/1')"> 
              <v-icon>
                mdi-map
              </v-icon>
              Voir sur la carte 
            </v-btn>
            &nbsp;&nbsp;&nbsp;&nbsp;
            <v-btn color="primary" @click="dialog1 = true">
              <v-icon>
                mdi-download
              </v-icon>
              exporter les données
            </v-btn>
          </v-toolbar>
        </template>
        <template v-slot:item.reponses="{ item }">
            <v-btn text @click="dialog = true" color="primary">
              <v-icon>
                mdi-clipboard-text
              </v-icon>
              Réponses
            </v-btn>
          </template>
          <template v-slot:no-data>
            <v-btn color="primary" @click="initialize">Reset</v-btn>
          </template>
        </v-data-table>
    </v-card>
      <v-dialog v-model="dialog" persistent max-width="600px">
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
    <v-dialog v-model="dialog1" persistent max-width="600px">
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
             Exporter les données
          </v-col>
        </v-card-title>
        <v-card-text>
          <v-col align="left">
            <h1 class="class1"> Choisir la format :</h1>
            <v-select
              :items="formats"
              label="Format"
              outlined
            ></v-select>
            <v-text-field
            label="Nom du Fichier"
            outlined
          ></v-text-field>
          </v-col>
        </v-card-text>
        <v-card-actions>
          <v-col align="center">
            <v-btn color="primary" width="90%" @click="dialog1 = false">Exporter</v-btn>
          </v-col>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
  export default {
    layout:'entreprise',
    data: () => ({
      dialog: false,
      headers: [
        {
          text: 'Nom',
          align: 'start',
          value: 'nom',
        },
        { text: 'Prénom', value: 'prenom' },
        { text: 'Lieu de Naissance', value: 'lieu_naissance' },
        { text: 'Tranche Age', value: 'tranche_age' },
        { text: 'Sexe', value: 'sexe' },
        { text: 'Latitude', value: 'latitude' },
        { text: 'Longitude', value: 'longitude' },
        { text: 'Réponses', value: 'reponses', sortable: false },
      ],
      dialog:false,
      dialog1:false,
      data: [],
      editedIndex: -1,
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
            reponse:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,",
        },
        {
            id:4,
            show:false,
            question:"question 4 ?",
            reponse:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,",
        },
        {
            id:5,
            show:false,
            question:"question 5 ?",
            reponse:"Oui",
        },
        {
            id:6,
            show:false,
            question:"question 6 ?",
            reponse:"Oui",
        },
        {
            id:7,
            show:false,
            question:"question 7 ?",
            reponse:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,",
        },
        {
            id:8,
            show:false,
            question:"question 8 ?",
            reponse:"Non",
        },
        {
            id:9,
            show:false,
            question:"question 9 ?",
            reponse:"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,",
        },
        {
            id:10,
            show:false,
            question:"question 10 ?",
            reponse:"Non",
        }
    ],
    formats: ['CSV', 'TSV', 'Excel', 'XML','Google Sheets'], 
    }),

    computed: {
    },

    watch: {
      dialog (val) {
        val || this.close()
      },
    },

    created () {
      this.initialize()
    },

    methods: {
      initialize () {
        let names = ['Junita' ,'Deveau','Karyn', 'Crew','Fidelia','Hemmer','Emmanuel','Woodrow','Israel','Markovich','Mercedez','Klatt','Delilah','Kiger','Alex','Edelstein','Hiedi','Nass','Sharyl','Jeffords'] ;
        let sexes = ['Homme','Femme']
        for (let index = 0; index < 60; index++) {
          this.data[index] = { 
              nom: names[Math.ceil(Math.random() * 20)-1],
              prenom: names[Math.ceil(Math.random() * 20)-1],
              lieu_naissance: 'Chlef',
              tranche_age: '24-28',
              sexe: sexes[Math.ceil(Math.random() * 2 )-1],
              latitude:Math.random() * 18,
              longitude:Math.random() * 18,
          };
        }
      },

      editItem (item) {
        this.editedIndex = this.desserts.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialog = true
      },

      deleteItem (item) {
        const index = this.desserts.indexOf(item)
        confirm('Are you sure you want to delete this item?') && this.desserts.splice(index, 1)
      },

      close () {
        this.dialog = false
        this.$nextTick(() => {
          this.editedItem = Object.assign({}, this.defaultItem)
          this.editedIndex = -1
        })
      },

      save () {
        if (this.editedIndex > -1) {
          Object.assign(this.desserts[this.editedIndex], this.editedItem)
        } else {
          this.desserts.push(this.editedItem)
        }
        this.close()
      },
    },
  }
</script>

<style scoped>
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
.headline{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-size: 32px;
}
.class1{
    color: black;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    font-size: 20px;
    margin-bottom: 10px;
}
</style>