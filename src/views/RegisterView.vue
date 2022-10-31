<template>
    <v-app id="inspire">
        <v-content>
            <v-container fluid fill-height>
                <v-layout align-center justify-center>
                    <v-flex xs12 sm8 md4>
                        <v-card class="elevation-12">
                            <v-toolbar dark color="primary">
                                <v-toolbar-title>Logowanie</v-toolbar-title>
                                <v-spacer />
                                <v-tooltip right>
                                </v-tooltip>
                            </v-toolbar>
                            <v-card-text>
                                <v-form ref="login" v-model="valid">
                                    <v-text-field @keyup.enter="submit" :rules="notEmptyRule" v-model="login"
                                        name="login" label="Login" type="text"></v-text-field>
                                    <v-text-field @keyup.enter="submit" :rules="notEmptyRule" v-model="password"
                                        id="password" name="password" label="Hasło" type="password"></v-text-field>
                                        <v-text-field @keyup.enter="submit" :rules="emailRules" v-model="mail" id="mail" name="mail" label="E-mail"
                                            type="email" required></v-text-field>
                                </v-form>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer />
                                <v-btn color="primary" @click.native="backToLoginScreen">Powrót</v-btn>
                                <v-btn color="primary" @click.native="submit" :disabled="!valid">Zarejestruj</v-btn>
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
            login: null,
            password: null,
            valid: false,
            mail: null,
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