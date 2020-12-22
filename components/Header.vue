<template>
  <div>
    <v-app-bar app color="primary darken-3" dark>
      <v-toolbar-title>Shimagami's Portfolio</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-toolbar-items class="d-none d-sm-flex">
        <v-btn
          x-large
          text
          class="text-capitalize"
          v-for="button in buttons"
          @click="$vuetify.goTo(`#${button.id}`)"
          :key="button.id"
          >{{ button.text }}</v-btn
        >
      </v-toolbar-items>

      <v-app-bar-nav-icon
        v-if="$vuetify.breakpoint.xs"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer
      right
      color="white"
      v-if="$vuetify.breakpoint.xs"
      app
      v-model="drawer"
    >
      <v-list>
        <v-list-item
          v-for="button in buttons"
          :key="button.id"
          @click="
            $vuetify.goTo(`#${button.id}`)
            drawer = false
          "
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
          id: 'first-work',
          text: 'Work#1',
          icon: 'mdi-numeric-1-circle-outline',
        },
        {
          id: 'second-work',
          text: 'Work#2',
          icon: 'mdi-numeric-2-circle-outline',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped></style>
