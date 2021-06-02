<template>
  <v-app>
    <v-card width="400" class="mx-auto mt-5">
      <v-card-title>
        <h1 class="display-1">Login</h1>
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field
              prepend-icon="mdi-account-circle"
              label="Username"/>
          <v-text-field
              type="password"
              label="Password"
              prepend-icon="mdi-lock"
              append-icon="mdi-eye-off"
          />
        </v-form>
      </v-card-text>
      <v-card-actions>
        <v-btn color="success">Register</v-btn>
        <v-btn color="info">Login</v-btn>
      </v-card-actions>
    </v-card>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    //
  }),
};
</script>
