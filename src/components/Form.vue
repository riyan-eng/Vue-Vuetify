<template>
    <div class="mt-5">
        <v-container>
            <v-card>
                <v-form v-model="isValid">
                    <v-card-title class="my-3">
                        <h1>Masuk</h1>
                    </v-card-title>
                    <v-card-text>
                        <v-text-field :rules="usernameRule" v-model="user.username" prepend-icon="mdi-account-circle" label="Username">
                        </v-text-field>
                        <v-text-field :rules="passwordRule" v-model="user.password" prepend-icon="mdi-lock"
                            :type="displayPassword ? 'text' : 'password'" label="Password"
                            :append-inner-icon="displayPassword ? 'mdi-eye' : 'mdi-eye-off'"
                            @click:append-inner="onDisplayPass"></v-text-field>
                    </v-card-text>
                    <v-card-actions>
                        <v-row align="center" justify="space-around">

                            <v-btn depressed type="submit" color="primary" @click.prevent="onSubmit" :disabled="!isValid">
                                Login
                            </v-btn>
                            <v-btn depressed color="error">
                                Register
                            </v-btn>

                        </v-row>
                    </v-card-actions>

                </v-form>
            </v-card>

        </v-container>
    </div>
</template>

<script>
export default {
    data() {
        return {
            displayPassword: false,
            user: {
                username: '',
                password: ''
            },
            usernameRule:[
                value => value != '' || 'Username is required'
            ],
            passwordRule:[
                value => value != '' || 'Password is required',
                value => value.length >= 6 || 'Minimal 6 character'
            ],
            isValid : false
        }
    },
    methods: {
        onDisplayPass() {
            this.displayPassword = !this.displayPassword
        },

        onSubmit() {
            console.log(this.user)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>