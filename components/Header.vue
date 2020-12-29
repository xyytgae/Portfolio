<template>
  <div>
    <v-app-bar app color="primary darken-3" dark>
      <v-app-bar-nav-icon
        v-if="$vuetify.breakpoint.sm || $vuetify.breakpoint.xs"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>Shimagami's Portfolio</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items
        v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs"
      >
        <v-btn
          x-large
          text
          class="text-capitalize"
          v-for="button in buttons"
          @click="clickButton(button)"
          :key="button.id"
          >{{ button.text }}</v-btn
        >
      </v-toolbar-items>
    </v-app-bar>

    <v-navigation-drawer
      right
      color="white"
      v-if="$vuetify.breakpoint.sm || $vuetify.breakpoint.xs"
      app
      v-model="drawer"
    >
      <v-list>
        <v-list-item
          v-for="button in buttons"
          :key="button.id"
          @click="clickButton(button.id)"
        >
          <v-list-item-action>
            <v-icon>{{ button.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="text-capitalize">{{
              button.text
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      buttons: [
        {
          id: 'profile',
          text: 'profile',
          icon: 'mdi-account',
        },
        {
          id: 'background',
          text: 'background',
          icon: 'mdi-briefcase',
        },
        {
          id: 'skills',
          text: 'skills',
          icon: 'mdi-laptop-windows',
        },
        {
          id: 'firstWork',
          text: 'Work#1',
          icon: 'mdi-numeric-1-circle-outline',
        },
        {
          id: 'secondWork',
          text: 'Work#2',
          icon: 'mdi-numeric-2-circle-outline',
        },
        {
          id: 'contact',
          text: 'contact',
          icon: 'mdi-numeric-2-circle-outline',
        },
      ],
    }
  },
  methods: {
    clickButton(button) {
      this.$vuetify.goTo(`#${button.id}`)
      this.drawer = false
    },
  },
}
</script>

<style lang="scss" scoped></style>
