<template>
  <div>
    <v-toolbar
      dark
      prominent
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Juan Alcoba</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn @click="logOut" icon>
        <v-icon>mdi-export</v-icon>
      </v-btn>
    </v-toolbar>
  </div>
</template>

<script>
export default {
    methods: {
    logOut(){
      this.$router.push('/login')
    }
  }
};
</script>

<style scoped></style>
