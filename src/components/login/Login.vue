<template>
    <div>
        <b-container style="padding-top: 150px">
            <b-row class="justify-content-md-center baseStyle">
                <label style="font-size: 50px">Chef Login</label>
            </b-row>
            <b-row class="justify-content-md-center baseStyle">
                <b-col lg="2">
                    <label class="fontStyle">Username:</label>
                </b-col>
                <b-col lg="6">
                    <b-form-input type="text" size="lg" placeholder="Enter username" @input="getUsername"></b-form-input>
                </b-col>
            </b-row>
            <b-row class="justify-content-md-center baseStyle">
                <b-col lg="2">
                    <label class="fontStyle">Password:</label>
                </b-col>
                <b-col lg="6">
                    <b-form-input type="password" size="lg" placeholder="Enter password" @input="getPassword"></b-form-input>
                </b-col>
            </b-row>
            <b-row class="justify-content-md-center baseStyle">
                <b-col lg="5">
                    <b-button block pill variant="warning" size="lg" @click="chefLogin">Confirm</b-button>
                </b-col>
            </b-row>
            <b-alert v-model="showDismissibleAlert" variant="danger" dismissible>
                {{message}}
            </b-alert>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "Login",
        data() {
            return {
                username: '',
                password: '',
                showDismissibleAlert: false,
                message: ''
            }
        },
        methods: {
            getUsername(value) {
                this.username = value;
                // eslint-disable-next-line no-console
                //console.log(value);
            },
            getPassword(value) {
                this.password = value;
                // eslint-disable-next-line no-console
                //console.log(value);
            },
            chefLogin() {
                if(this.username === '') {
                    this.showDismissibleAlert = true;
                    this.message = 'Username is empty!';
                } else if(this.password === '') {
                    this.showDismissibleAlert = true;
                    this.message = 'Password is empty!';
                } else {

                }
            }
        }
    }
</script>

<style scoped>
    .fontStyle {
        line-height: 48px;
        font-size: larger;
    }

    .baseStyle {
        padding-top: 20px;
    }
</style>