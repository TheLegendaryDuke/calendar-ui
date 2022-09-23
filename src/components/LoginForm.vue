<template>
  <v-container>
    <div class="bgImage"/>
    <v-card
      elevation="12"
      outlined
      class="login"
    >
      <v-card-title>
        <v-tabs
            fixed-tabs
            background-color="indigo"
            dark
        >
          <v-tab>
            Login
          </v-tab>
          <v-tab>
            Register
          </v-tab>
        </v-tabs>
      </v-card-title>
    </v-card>
  </v-container>
</template>

<script>
  export default {
    name: 'LoginForm',
    data: () => ({

    }),
  }
</script>

<style>
  .bgImage {
    background-image: url("~@/assets/background.jpg");
    height: 100%;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    filter: blur(5px);
  }

  .login {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>