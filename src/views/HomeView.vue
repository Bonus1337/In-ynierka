<template>
  <v-app id="inspire"> 
    <v-content>
      <v-container fluid fill-height>
        
        <v-layout align-center justify-center>
          <v-flex xs12 sm8 md4>
            <div class="side-bar-card">
              <h2>Platforma do obsługi praktyk zawodowych Państwowej Uczelni Zawodowej im. Ignacego Mościckiego w Ciechanowie</h2>
              <v-img class="middle-of-box" max-height="100" max-width="100" src="../../public/logo.jpeg"></v-img>
            </div>
          </v-flex>
          <v-flex xs12 sm8 md4>            
            <v-card class="elevation-12">
              <v-toolbar dark color="primary">
                <v-spacer></v-spacer>
                <v-toolbar-title>Logowanie</v-toolbar-title>
                <v-spacer />
                <v-tooltip right>
                </v-tooltip>
              </v-toolbar>
              <v-card-text>
                <v-form ref="login" v-model="valid">
                  <v-text-field @keyup.enter="submit" :rules="notEmptyRule" v-model="login" 
                    name="login" label="Login" type="text"></v-text-field>
                  <v-text-field @keyup.enter="submit" :rules="notEmptyRule" v-model="password" id="password"
                    name="password" label="Hasło" type="password"></v-text-field>
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer />
                <v-btn color="success" @click.native="submit" :disabled="!valid">Zaloguj</v-btn>
                <v-btn color="warning" @click="register">Zarejestruj</v-btn>
                <v-spacer />
              </v-card-actions>
            </v-card>
            
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
    <v-footer color="primary lighten-1" padless>
      <v-row justify="center" no-gutters>
        <v-btn 
        color="white" 
        text 
        rounded 
        class="my-2" 
        href="https://puzim.edu.pl/"
        target="_blank">
          <v-icon>mdi-web</v-icon>
        </v-btn>
        <v-btn 
        color="white" 
        text 
        rounded 
        class="my-2" 
        href="https://www.facebook.com/PUZCiechanow" 
        target="_blank">
        <v-icon>mdi-facebook</v-icon>
        </v-btn>
                <v-btn 
                color="white" 
                text rounded 
                class="my-2" 
                href="https://www.youtube.com/channel/UCcdw2L4TBY-SZx6D7RHQpJA" 
                target="_blank">
                  <v-icon>mdi-youtube</v-icon>
                </v-btn>
      
        <v-btn 
        color="white" 
        text rounded 
        class="my-2" 
        href="  https://www.instagram.com/puzim_uczymypomagac/" 
        target="_blank">
        <v-icon>mdi-instagram</v-icon>  
        </v-btn>
        <v-btn 
        color="white" 
        text rounded 
        class="my-2" 
        href="https://puzim.edu.pl/uczelnia/kontakty" 
        target="_blank">
          <v-icon>mdi-phone</v-icon>
        </v-btn>

        
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} — <strong>PUZ Ciechanów</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      notEmptyRule: [
        v => !!v || 'Pole nie może być puste'
      ],
      login: null,
      password: null,
      valid: false
    }
  },
  methods: {
    submit() {
      if (this.$refs.login.validate()) {
        localStorage.setItem('loggedIn', this.login)
        this.$router.push("/dashboard")
      }
    },
    register() {
        this.$router.push("/register")
    }
  }
}
</script>
<style scoped>
.middle-of-box {
  margin: auto;
}
.side-bar-card{
  text-align: center;
  color: white;
}
#inspire{
  background-color: #8BC6EC;
  background-image: linear-gradient(135deg, #8BC6EC 0%, #9599E2 100%);
}
</style>