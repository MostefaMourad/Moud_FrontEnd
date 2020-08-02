<template>
  <v-card
    class="mx-auto"
    max-width="344"
    dense
  >
    <v-img
      src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
      height="130px"
    ></v-img>

    <v-card-title>
        {{tache.titre}}
    </v-card-title>
    <v-card-subtitle>
            {{tache.region}} , {{tache.nbr_personne}} Personne
    </v-card-subtitle>
    <v-card-actions>
        <v-chip 
            class="ma-2"
            color="secondary"
            >
            {{tache.prix}}
        </v-chip>
        <v-spacer></v-spacer>
        <v-btn
            color="primary"
            text
        >
            Détails
        </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      tache : {
          titre:"Nom de la tâche",
          prix:"6000 DA",
          nbr_personne:60,
          region:"Oran"
      }
    }),
  }
</script>

<style scoped>
.titre{
    font-size: 16px;
}
</style>