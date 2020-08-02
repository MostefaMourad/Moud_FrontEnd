<template>
    <v-container fill-height fluid>
        <v-row align="center"
               justify="center" >
            <v-col md="6" align="center">
                <img src="~/assets/login_1.png" alt="" height="500">  
                <h1 class="grey--text"> Besoin d'aide ? <a href="/contactus" class="link"> Nous Contacter</a> </h1> 
                </v-col>
            <v-col md="6" align="center">
                <v-card
                dark
                flat
                >
                <v-card-title>
                    <v-col align="center">
                        <h1 class="titre">
                            Connectez-vous en tant qu'entreprise
                        </h1>
                    </v-col> 
                </v-card-title>
                <v-spacer></v-spacer>
                <v-card-text>
                    <v-form>
                        <v-row>
                        <v-col align="center">
                            <v-text-field
                                label="Email"
                                name="login"
                                prepend-icon="mdi-account"
                                type="text"
                                v-model="email"
                            ></v-text-field>
                        </v-col>
                        </v-row>
                        <v-row>
                        <v-col align="center"> 
                            <v-text-field
                                id="password"
                                label="Mot de Passe"
                                name="password"
                                v-model="password"
                                prepend-icon="mdi-lock"
                                :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                :type="show1 ? 'text' : 'password'"
                                hint="Au moins 8 caractères"
                                counter
                                @click:append="show1 = !show1"  
                            ></v-text-field>
                        </v-col>
                        </v-row>
                    </v-form>
                </v-card-text>
                <v-spacer></v-spacer>
                <v-card-actions>
                    <v-col align="center">
                        <v-btn
                        light
                        width="90%"
                        @click="$router.push('/partner/accueil')"
                        >
                        S'identifier 
                        </v-btn>
                    </v-col>
                </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        data() {
            return {
                email:'',
                password:'',
                show1:false,
            }
        },
    }
</script>

<style scoped>
.link{
  text-decoration: none;
}
.link:hover{
    text-decoration: underline;
}
.titre{
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-size: 35px;  
  width: 70%;
}
</style>