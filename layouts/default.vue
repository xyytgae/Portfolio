<template>
  <v-app dark>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>PortfolioSite</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items>
        <v-btn text @click="$vuetify.goTo('#profile')">プロフィール</v-btn>
        <v-btn text @click="$vuetify.goTo('#background')">経歴</v-btn>
        <v-btn text @click="$vuetify.goTo('#languages')"
          >学習している言語</v-btn
        >
        <v-btn text @click="$vuetify.goTo('#first-work')">作品#1</v-btn>
        <v-btn text @click="$vuetify.goTo('#second-work')">作品#2</v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer app color="primary" dark>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {}
  },
}
</script>
