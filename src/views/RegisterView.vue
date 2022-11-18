<template>
    <v-app id="inspire">
        <v-content>
            <v-container fluid fill-height>
                <v-layout align-center justify-center>
                    <v-flex xs12 sm8 md4>
                        <v-card class="elevation-12">
                            <v-toolbar dark color="info">
                                <v-spacer></v-spacer>
                                <v-toolbar-title>Rejestracja</v-toolbar-title>
                                <v-spacer />
                                <v-tooltip right>
                                </v-tooltip>
                            </v-toolbar>
                            <v-card-text>
                                <v-form 
                                ref="login" 
                                v-model="valid">
                                    <v-text-field 
                                    @keyup.enter="submit" 
                                    :rules="notEmptyRule" 
                                    v-model="name"
                                    name="imie" 
                                    label="Imie" 
                                    type="text"></v-text-field>
                                        <v-text-field 
                                        @keyup.enter="submit" 
                                        :rules="notEmptyRule" 
                                        v-model="secName" 
                                        name="Nazwisko" 
                                        label="Nazwisko" 
                                        type="text">
                                        </v-text-field>

                                        <v-text-field 
                                        @keyup.enter="submit" 
                                        :rules="emailRules" 
                                        v-model="mail" 
                                        id="mail" 
                                        name="mail" 
                                        label="E-mail uczelniany"
                                        type="email" required></v-text-field>
                                            <v-text-field 
                                            @keyup.enter="submit" 
                                            :rules="notEmptyRule" 
                                            v-model="key" 
                                            name="key" 
                                            label="Kod rejestracji"
                                            type="text">
                                            </v-text-field>
                                        <v-text-field 
                                        @keyup.enter="submit" 
                                        :rules="passwordRules" 
                                        v-model="password" 
                                        id="password" 
                                        name="password"
                                        label="Hasło" 
                                        type="password"></v-text-field>
                                        <v-text-field 
                                        @keyup.enter="submit" 
                                        :rules="confirmPasswordRules" 
                                        v-model="confirmPassword" 
                                        id="confirmPassword"
                                        name="confirmPassword" 
                                        label="Powtórz hasło" 
                                        type="password"></v-text-field>
                                </v-form>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer />
                                <v-btn 
                                color="error" 
                                @click.native="backToLoginScreen">Powrót</v-btn>
                                <v-btn 
                                color="success" 
                                @click.native="submit" 
                                :disabled="!valid">Zarejestruj</v-btn>
                                <v-spacer />
                            </v-card-actions>
                        </v-card>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
export default {
    data() {
        return {
            notEmptyRule: [
                v => !!v || 'Pole nie może być puste'
            ],
            emailRules: [
                v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail musi być poprawny'
            ],
            passwordRules: [
                (value) => !!value || 'Wpisz haslo',
                (value) => (value && value.length >= 9) || 'Haslo musi zawierać minimum 9 znaków',
            ],
            confirmPasswordRules: [
                (value) => !!value || 'Wpisz haslo ponownie',
                (value) =>
                    value === this.password || 'Hasła się nie zgadzają',
            ],
            name: null,
            password: null,
            valid: false,
            mail: null,
            secName: null,
            confirmPassword: null,
            key: null
        }
    },
    methods: {
        submit() {
            if (this.$refs.login.validate()) {
                this.$router.push("/")
            }
        },
        backToLoginScreen() {
            this.$router.push("/")
        }
    }
}
</script>

<style scoped>
.center-image {
    background-color: red;
}
#inspire {
    background-color: #8BC6EC;
    background-image: linear-gradient(135deg, #8BC6EC 0%, #9599E2 100%);
}

</style>