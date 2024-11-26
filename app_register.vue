<template>
    <div style="background-color: gray;">
        <div class="area">
            <div class="box">
                <svg xmlns="http://www.w3.org/2000/svg" width="2.5em" height="2.5em" viewBox="0 0 24 24" style="margin-top: 25px; margin-left: 35px;">
                    <path fill="white" d="M7 12a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0" />
                </svg>
                <h1 style="margin-left: 35px; color: white;">Let's<br>
                <b>Create<br>
                Yoour<br>
                Account</b></h1>
            </div>
            <v-form fast-fail @submit.prevent>
                <v-text-field
                    v-model="firstName"
                    :rules="firstNameRules"
                    label="Full Name"
                    style="margin-top: 50px; padding-left: 50px; padding-right: 50px;"
                    prepend-inner-icon="mdi mdi-account"
                    variant="outlined"
                ></v-text-field>

                <v-text-field
                    v-model="firstName"
                    :rules="firstNameRules"
                    label="Email Adress"
                    style="padding-left: 50px; padding-right: 50px;"
                    prepend-inner-icon="mdi mdi-email"
                    variant="outlined"
                ></v-text-field>

                <v-text-field
                    v-model="firstName"
                    :rules="firstNameRules"
                    label="Password"
                    style="padding-left: 50px; padding-right: 50px;"
                    prepend-inner-icon="mdi mdi-lock"
                    variant="outlined"
                ></v-text-field>

                <v-text-field
                    v-model="lastName"
                    :rules="lastNameRules"
                    label="Retype Password"
                    style="padding-left: 50px; padding-right: 50px;"
                    prepend-inner-icon="mdi mdi-lock"
                    variant="outlined"
                ></v-text-field>

                <v-checkbox style="margin-left: 40px;" label="I agree to the Terms & Privacy"></v-checkbox>

                <v-btn style="background-color: #006633; color: white; width: 500px; height: 50px; margin-left: 50px; border-radius: 45px;" class="" type="submit" >Sign Up</v-btn>
                <p style="margin-top: 25px; margin-left: 40px;">Have an account? <b>Sign in</b></p>
            </v-form>
        </div>
    </div>
</template>

<style>
    .area{
        height: 1000px;
        width: 600px;
        background-color: white;
        border-top-left-radius: 50px;
        border-top-right-radius: 50px;
        border-bottom-left-radius: 50px;
        border-bottom-right-radius: 50px;
        margin-bottom: 50px;
        
    }

    .box{
        height: 300px;
        width: 600px; 
        background-color: #006633;
        border-bottom-left-radius: 50px;
        border-bottom-right-radius: 50px;
        
    }
</style>