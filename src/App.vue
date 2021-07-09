<template>
  <v-app>
    <div class="container">
    <div class="container"><nav-bar></nav-bar></div>

    <v-main>
      <HelloWorld/>
    </v-main>
    </div>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import NavBar from './components/shared/Navbar';

export default {
  name: 'App',

  components: {
    HelloWorld,
    NavBar,

  },

  data: () => ({
    //
  }),
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');


.container {
    width: 100%;
    padding: 12px;
    margin-right: auto;
    margin-left: auto;
}
@media (min-width: 924px){
.container {
    max-width: 924px!important;
}}

.v-toolbar__content, .v-toolbar__extension {
    align-items: center;
    display: flex;
    position: relative;
    z-index: 0;
}
.v-toolbar__content, .v-toolbar__extension {
    padding: 4px 0;
}

.v-application--wrap {
  font-family: 'Open Sans', sans-serif;
}
.headline,
.title,
.subheading{
     font-family: 'Open Sans', sans-serif !important;
}
.theme--light.v-app-bar.v-toolbar.v-sheet{
  background-color: white;
}

</style>
