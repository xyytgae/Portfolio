<template>
  <v-card color="grey lighten-2" flat>
    <v-card-text class="pb-0 text-center">Skills</v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">習得した技術</span></v-card-text
    >

    <v-container class="px-0">
      <v-row justify="center">
        <v-card
          v-for="firstSkill in firstSkills"
          :key="firstSkill.name"
          class="text-center sheet"
          color="grey lighten-2"
          flat
        >
          <v-container>
            <img class="img" :src="firstSkill.src" />
            <h3 class="my-3">{{ firstSkill.name }}</h3>
          </v-container>
        </v-card>
      </v-row>

      <v-row justify="center">
        <v-card
          v-for="secondSkill in secondSkills"
          :key="secondSkill.name"
          class="text-center sheet"
          color="grey lighten-2"
          flat
        >
          <v-container>
            <img class="img" :src="secondSkill.src" />
            <h3 class="my-3">{{ secondSkill.name }}</h3>
          </v-container>
        </v-card>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      firstSkills: [
        {
          src: require('~/assets/images/skills/html-5.svg'),
          name: 'HTML',
        },
        {
          src: require('~/assets/images/skills/css-3.svg'),
          name: 'CSS',
        },
        {
          src: require('~/assets/images/skills/javascript.svg'),
          name: 'JavaScript',
        },
        {
          src: require('~/assets/images/skills/typescript.svg'),
          name: 'TypeScript',
        },
      ],
      secondSkills: [
        {
          src: require('~/assets/images/skills/vuejs.svg'),
          name: 'Vue.js',
        },
        {
          src: require('~/assets/images/skills/vuetifyjs.svg'),
          name: 'Vuetify.js',
        },
        {
          src: require('~/assets/images/skills/nuxtjs.svg'),
          name: 'Nuxt.js',
        },
        {
          src: require('~/assets/images/skills/firebase.svg'),
          name: 'Firebase',
        },
      ],
    }
  },
}
</script>
