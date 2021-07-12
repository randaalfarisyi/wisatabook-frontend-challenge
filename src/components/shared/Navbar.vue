<template>
    

<v-app-bar
      app
    >
    <div class="container">
      <div class="d-flex align-center" style="">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src=""
          transition="scale-transition"
          width="40"
        />

      
        <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-icon v-if="!$vuetify.theme.dark" class="mr-4">mdi-theme-light-dark</v-icon>
      <v-icon v-if="$vuetify.theme.dark" class="mr-4" color="blue">mdi-theme-light-dark</v-icon>
      <v-switch class="pt-5 mr-10"
        v-model="$vuetify.theme.dark"
        inset
            >
        </v-switch>
  
  </div>
  </div>
    </v-app-bar>


</template>

<script>
export default {
    name: 'NavBar',
    data () {
      return {
        checkbox: true,
      }
    },
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    }
}
</script>