<template>
    <div class="mt-5">
        <v-container>
            <v-card>
                <v-form @submit.prevent="onSubmit">
                    <v-card-title class="my-3">
                        <h1>Masuk</h1>
                    </v-card-title>
                    <v-card-text>
                        <v-text-field v-model="user.username" prepend-icon="mdi-account-circle" label="Username">
                        </v-text-field>
                        <v-text-field v-model="user.password" prepend-icon="mdi-lock"
                            :type="displayPassword ? 'text' : 'password'" label="Password"
                            :append-inner-icon="displayPassword ? 'mdi-eye' : 'mdi-eye-off'"
                            @click:append-inner="onDisplayPass"></v-text-field>
                    </v-card-text>
                    <v-card-actions>
                        <v-row align="center" justify="space-around">

                            <v-btn depressed type="submit" color="primary">
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
            }
        }
    },
    methods: {
        onDisplayPass() {
            this.displayPassword = !this.displayPassword
        },

        onSubmit() {
            console.log(this.user.username)
        }
    }
}
</script>

<style lang="scss" scoped>

</style>