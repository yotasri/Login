<template>
    <div style="background-color: gray;">
        <v-container class="d-flex align-center justify-center" style="height: 100vh; width: 600px; background-color: white;" >
            <v-row class="flex-child text-subtitle-3">
            <v-col
                class="d-flex"
                cols="12"
                md="4"
                >
                <v-sheet
                    class="d-flex"
                    height="20"
                    style=""
                    >
                    <sheet-footer>
                        <div style="margin-top: 250px; margin-left: 20px;">
                            <svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 24 24">
                                <path fill="black" d="M7 12a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0" />
                            </svg>
                        </div>
                    </sheet-footer>
                </v-sheet>
                <v-sheet
                    class="d-flex"
                    height="20"
                    style=""
                    >
                    <sheet-footer>
                        <div style="margin-top: 250px; margin-left: 470px;">
                            <svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 24 24">
                                <path fill="black" d="M6.4 19L5 17.6l5.6-5.6L5 6.4L6.4 5l5.6 5.6L17.6 5L19 6.4L13.4 12l5.6 5.6l-1.4 1.4l-5.6-5.6z" />
                            </svg>
                        </div>
                    </sheet-footer>
                </v-sheet>
            </v-col>  

            <div style="">
                <v-sheet
                    class="d-flex"
                    height="250"
                    style=""
                    >
                    <sheet-footer>
                        <div class="icon">
                            <svg xmlns="http://www.w3.org/2000/svg" width="10em" height="10em" viewBox="0 0 24 24">
                                <g fill="none">
                                    <path d="m12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035q-.016-.005-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427q-.004-.016-.017-.018m.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093q.019.005.029-.008l.004-.014l-.034-.614q-.005-.018-.02-.022m-.715.002a.02.02 0 0 0-.027.006l-.006.014l-.034.614q.001.018.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01z" />
                                    <path fill="currentColor" d="M12 2a6 6 0 0 1 5.996 5.775L18 8h1a2 2 0 0 1 1.995 1.85L21 10v10a2 2 0 0 1-1.85 1.995L19 22H5a2 2 0 0 1-1.995-1.85L3 20V10a2 2 0 0 1 1.85-1.995L5 8h1a6 6 0 0 1 6-6m7 8H5v10h14zm-7 2a2 2 0 0 1 1.134 3.647l-.134.085V17a1 1 0 0 1-1.993.117L11 17v-1.268A2 2 0 0 1 12 12m0-8a4 4 0 0 0-4 4h8a4 4 0 0 0-4-4" />
                                </g>
                            </svg>
                            <h1><b>Forgot</b></h1>
                            <h1>Password?</h1>
                            <p>no worries, we'll send you</p>
                            <p>reset instruction</p>
                        </div>
                    </sheet-footer>
                </v-sheet>
            </div>
                
                <v-form class="form">
                    <h3 class="text_1">Email</h3>
                    <v-text-field
                        density="comfortable"
                        placeholder="Enter your Email"
                        prepend-inner-icon="mdi mdi-email"
                        variant="outlined"
                        class="mb-8"
                        outlined
                    
                        hide-details
                        style="color: white; margin-left: 45px; width: 500px; border-radius: 20px;"
                    ></v-text-field>

                    <v-btn
                        size="x-large"
                        variant="elevated"
                        
                        style="border-radius: 16px; text-transform: none; font-weight: bold; font-size: 1.2rem; padding-left: 10px; width: 500px; margin-left: 45px;"
                        
                    >
                    Reset Password
                    </v-btn>
                    <h3 class="text_2">Back to Login</h3>
                    <svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 24 24" style="margin-top: 30px; margin-left: 285px;">
                        <path fill="white" d="m7 12l5-5v3h4v4h-4v3zm14-7v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2m-2 0H5v14h14z" />
                    </svg>
                </v-form>
            </v-row>
        </v-container>
    </div>
</template>

<style>

    .form{
        background-color: #006633;
        width: 600px;
        padding-top: 50px;
        padding-bottom: 280px;
        margin-top: 500px;
       margin-left: auto;
       margin-right: auto;
       border-top-left-radius: 50px;
       border-top-right-radius: 50px;
       
       
    }

    .text_1{
        color: white;
        margin-bottom: 7px;
        margin-left: 50px;

    }

    .text_2{
        color: white;
        text-align: center;
        margin-top: 50px;
    }

    .icon{
        margin-top: 350px;
        margin-left: 3px;
        text-align: center;
    }

    
</style>