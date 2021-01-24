<template>
  <v-container>
    <v-card class="mx-16 my-6 pa-6 text-center">
      <h2>Register</h2>
      <p>
        sudah punya akun? silahkan
        <v-btn small color="primary" text class="mx-0 px-0" to="/login"
          >Login</v-btn
        >
      </p>

      <v-form ref="form" v-model="valid" lazy-validation>
        <v-text-field
          v-model="email"
          :rules="emailRules"
          label="E-mail"
          required
        ></v-text-field>

        <v-text-field
          autocomplete="current-password"
          :value="userPassword"
          label="Enter password"
          hint="Your password passed! Password rules are not meant to be broken!"
          :append-icon="value ? 'mdi-eye' : 'mdi-eye-off'"
          @click:append="() => (value = !value)"
          :type="value ? 'password' : 'text'"
          :rules="[rules.password]"
          @input="(_) => (userPassword = _)"
        ></v-text-field>

        <div class="mt-10 mb-6">
          <v-btn color="primary" class="mx-2"> register </v-btn>

          <v-btn color="error" class="mx-2" @click="reset"> Reset Form </v-btn>
        </div>
      </v-form>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],

    userPassword: '',
    valid: true,
    value: true,
    rules: {
      required: (value) => !!value || 'Required.',
      password: (value) => {
        const pattern = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\$%\^&\*])(?=.{8,})/
        return (
          pattern.test(value) ||
          'Min. 8 characters with at least one capital letter, a number and a special character.'
        )
      },
    },
  }),
  methods: {
    validate() {
      this.$refs.form.validate()
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
  },
}
</script>

<style></style>
