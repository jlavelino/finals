<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3" color="blue-grey-lighten-1">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-row>
            <v-col cols="12" md="6" class="mx-auto py-10">
              <v-card class="mx-auto" prepend-icon="mdi-login" subtitle="Login Form">
                <template v-slot:title>
                  <span class="font-weight-black">AcaTrail</span>
                </template>

                <v-card-text class="bg-surface-light pt-4">
                  <v-sheet class="mx-auto" width="300">
                    <v-form fast-fail @submit.prevent>
                      <v-text-field label="Email" variant="outlined"></v-text-field>

                      <v-text-field
                        label="Password"
                        type="password"
                        variant="outlined"
                      ></v-text-field>

                      <v-btn
                        class="mt-2"
                        type="submit"
                        block
                        color="primary"
                        prepend-icon="mdi-login"
                        >Submit</v-btn
                      >
                    </v-form>
                  </v-sheet>
                  <v-divider></v-divider>
                  <h5 class="text-center my-3">
                    Don't have account? Click here to
                    <RouterLink to="/register">Register</RouterLink>
                  </h5>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
      <v-footer color="blue-grey-lighten-1" border app>Copyright</v-footer>
    </v-app>
  </v-responsive>
</template>
