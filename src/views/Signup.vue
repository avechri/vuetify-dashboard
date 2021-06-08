<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Sign up</h1>
        <v-form>
          <v-text-field
            label="Email"
            type="email"
            v-model="email"
            :rules="emailRules"
            required
          />
          <v-autocomplete label="Which browser do you use?" :items="browsers" />
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ],
      browsers: ['Chrome', 'Safari', 'Mozilla Firefox', 'Microsoft Edge']
    }
  }
}
</script>

<style scoped></style>
