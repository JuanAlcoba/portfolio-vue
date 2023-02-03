<template>
  <v-container fluid >
  <v-card
  class="mx-auto"
  elevation="9"
  outlined
  width="600"
  >
  <v-form @submit.prevent="logIn"
    ref="form"
    v-model="valid"
    lazy-validation
  >
  <v-col>
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Nombre"
      required
    ></v-text-field>
  </v-col>
  <v-col>
    <v-text-field
      v-model="password"
      :rules="passwordRules"
      label="Password"
      required
    ></v-text-field>
  </v-col>

  <v-col>
    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      type="submit"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>
  </v-col>
  </v-form>
</v-card>
</v-container>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      password: '',
      passwordRules: [
        v => !!v || 'Password is required',
        v => v.length >= 8 || 'Password must be at least 8 characters',
      ],
    }),

    methods: {
      logIn(){
        const formData = {
        name: this.name,
        password: this.password
        }
        try{      
          console.log(formData);
          this.$router.push('/')
        } 
        catch {
          console.error('Error')
        }
      },
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
    },
  }
</script>

<style scoped>

</style>
