<template>
        <div style="background-color: gray; height: 1400px; justify-content: center;">
            <div class="area">
                <div>
                    <img src="/public/img/student-removebg-preview.png" style="margin-top: 25px; margin-left: 145px; height: 300px;">
                    <h1 style="font-size: 500%; color: #DAA520; margin-left: 145px; margin-top: 0px;">Student</h1>
                    <h1 style="color: white; margin-left: 200px;">CHECK APP</h1>
                    <v-form @submit.prevent>
                        <v-text-field
                            v-model="firstName"
                            :rules="rules"
                            label="Email or Phone"
                            style="padding-left: 50px; padding-right: 50px; margin-top: 50px; color: white;"
                            prepend-inner-icon="mdi mdi-email"
                            variant="outlined"
                        ></v-text-field>

                        <v-text-field
                            v-model="firstName"
                            :rules="rules"
                            label="Password"
                            style="padding-left: 50px; padding-right: 50px; color: white;"
                            prepend-inner-icon="mdi mdi-lock"
                            variant="outlined"
                        ></v-text-field>
                    </v-form>
                </div>

                
                <div class="box">
                    <p style="padding-top: 20px; margin-left: 222px;"><h3>Forgot Password?</h3></p>
                    <v-btn style="background-color: #006633; color: white; width: 500px; height: 50px; margin-left: 50px; margin-top: 25px; border-radius: 45px;" class="" type="submit" >Login</v-btn>
                    <p style="margin-top: 25px; margin-left: 290px;"><h3>or</h3></p>
                    <v-btn style="background-color: #778899; color: white; width: 500px; height: 50px; margin-left: 50px; margin-top: 25px; border-radius: 45px;" class="" type="submit" >Create an account</v-btn>

                </div>
                
            </div>
        </div>
</template>
<script>
</script>

<style>
    .area{
        padding-top: 20px;
        margin-top: 50px;
        height: 1200px;
        width: 600px;
        background-color: #006633;
        margin-left: 650px;
    }

    .box{
        margin-top: 50px;
        height: 450px;
        width: 600px; 
        background-color: white;
        border-top-left-radius: 50px;
        border-top-right-radius: 50px;
        
        
    }
</style>