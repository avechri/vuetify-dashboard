<template>
  <v-container>
    <v-row>
      <v-col cols="6">
        <h1>Sign up</h1>
        <v-form ref="signUpForm">
          <v-text-field
            label="Email"
            type="email"
            v-model="email"
            :rules="emailRules"
            required
          />
          <v-autocomplete label="Which browser do you use?" :items="browsers" />
          <v-file-input accept="image/*" label="Attach profile pic" />

          <v-menu
            ref="menu"
            v-model="menu"
            :close-on-content-click="false"
            :return-value.sync="birthdayDate"
            transition="scale-transition"
            offset-y
            min-width="auto"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                v-model="birthdayDate"
                label="Picker in menu"
                prepend-icon="mdi-calendar"
                readonly
                v-bind="attrs"
                v-on="on"
              ></v-text-field>
            </template>
            <v-date-picker v-model="birthdayDate" no-title scrollable>
              <v-spacer></v-spacer>
              <v-btn text color="primary" @click="menu = false">
                Cancel
              </v-btn>
              <v-btn
                text
                color="primary"
                @click="$refs.menu.save(birthdayDate)"
              >
                OK
              </v-btn>
            </v-date-picker>
          </v-menu>

          <v-checkbox
            label="Agree to sell my soul to the devil"
            v-model="agreeToTerms"
            :rules="agreeToTermsRules"
            required
          />

          <v-btn type="submit" color="primary">Submit</v-btn>
          <v-btn color="warning" @click="resetValidation"
            >Reset Validation</v-btn
          >
          <v-btn color="error" @click="resetForm">Reset</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      agreeToTerms: false,
      agreeToTermsRules: [
        value => !!value || 'You must agree to sign up an acc'
      ],
      email: '',
      emailRules: [
        value => !!value || 'E-mail is required',
        value => /.+@.+/.test(value) || 'E-mail must be valid'
      ],
      browsers: ['Chrome', 'Safari', 'Mozilla Firefox', 'Microsoft Edge'],
      birthdayDate: new Date().toISOString().substr(0, 10),
      menu: false
    }
  },
  methods: {
    resetForm() {
      this.$refs.signUpForm.reset()
    },
    resetValidation() {
      this.$refs.signUpForm.resetValidation()
    }
  }
}
</script>

<style scoped></style>
