<template>
  <v-container class="login">
    <v-card
        elevation="12"
        outlined
    >
      <v-card-title>
        <v-tabs
            fixed-tabs
            background-color="white"
            v-model="tab"
        >
          <v-tab>
            Login
          </v-tab>
          <v-tab>
            Register
          </v-tab>
        </v-tabs>
      </v-card-title>
      <v-card-text>
        <v-tabs-items v-model="tab">
          <v-tab-item>
            <v-form v-model="valid">
              <v-row dense>
                <v-col
                    cols="12"
                    md="4"
                >
                  <v-text-field
                      v-model="email"
                      :rules="emailRules"
                      label="E-mail"
                      required
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row dense>
                <v-col
                    cols="12"
                    md="4"
                >
                  <v-text-field
                      v-model="password"
                      label="Password"
                      :rules="requiredRule('Password')"
                      type="password"
                      required
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-form>
          </v-tab-item>
          <v-tab-item>
            <v-form v-model="valid">
              <v-container>
                <v-row>
                  <v-col
                      cols="12"
                      md="4"
                  >
                    <v-text-field
                        v-model="firstname"
                        :rules="requiredRule('First name')"
                        label="First name"
                        required
                    ></v-text-field>
                  </v-col>
                </v-row>
                <v-row>
                  <v-col
                      cols="12"
                      md="4"
                  >
                    <v-text-field
                        v-model="lastname"
                        :rules="requiredRule('Last name')"
                        label="Last name"
                        required
                    ></v-text-field>
                  </v-col>
                </v-row>
                <v-row>
                  <v-col
                      cols="12"
                      md="4"
                  >
                    <v-text-field
                        v-model="email"
                        :rules="emailRules"
                        label="E-mail"
                        required
                    ></v-text-field>
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
          </v-tab-item>
        </v-tabs-items>
      </v-card-text>
      <v-card-actions>
        <v-btn
            text
            @click="submit"
        >
          Submit
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
// @ is an alias to /src
export default {
  name: 'LoginView',
  components: {
  },
  data: () => {
    return {
      tab: null,
      valid: false,
      firstname: '',
      lastname: '',
      requiredRule: (name) => [
        v => !!v || name + ' is required'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
      password: '',
      confirmPassword: '',
    }
  }
}
</script>

<style>
  .login {
    position: absolute;
    width: 50%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>
