<template>
    <div class="container">
        <form v-if="!submitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Sign-up</h1>
                    <hr>

                    <app-full-name-input v-model="userData.fullName"></app-full-name-input>
                    <!--<div class="form-group">-->
                        <!--<label for="fullName">Full Name</label>-->
                        <!--<input-->
                                <!--type="text"-->
                                <!--id="fullName"-->
                                <!--class="form-control"-->
                                <!--v-model="userData.fullName">-->
                    <!--</div>-->
                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                                type="text"
                                id="email"
                                class="form-control"
                                v-model="userData.email">
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control"
                                v-model="userData.password">
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="store" v-model="storeInDb">
                        <label for="store">Store in Database?</label>
                    </div>
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            @click.prevent="submitted = true">Submit!
                    </button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{userData.fullName}}</p>
                        <p>Mail: {{userData.email}}</p>
                        <p>Password: {{userData.password}}</p>
                        <p>Store in Database?: {{storeInDb}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullNameInput from './FullNameInput.vue';

    export default {
        data () {
            return {
                userData: {
                    fullName: '',
                    email: '',
                    password: ''
                },
                storeInDb: false,
                submitted: false
            };
        },
        components: {
            appFullNameInput: FullNameInput
        }
    }
</script>

<style>
</style>
