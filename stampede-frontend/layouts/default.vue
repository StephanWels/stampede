<template>
  <v-app dark>
    <v-app-bar fixed app>
      <v-toolbar-title class="text-leckerli"><nuxt-link to="/"><b>StamP</b>ete</nuxt-link></v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn :ripple="false" to="/admin" icon>
        <v-icon>mdi-cloud-upload-outline</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer absolute app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      title: 'Vuetify.js',
    }
  },
}
</script>

