<template>
  <header>
    <nav>
      <v-toolbar color="indigo" dark fixed>
        <v-toolbar-title>{{ title }}</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn v-for="item in menu" :key="item.id" :to="item.link" text>{{
            item.title
          }}</v-btn>
        </v-toolbar-items>
        <v-menu class="hidden-md-and-up">
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
          <v-list>
            <v-list-tile v-for="item in menu" :key="item.id">
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>
        </v-menu>
      </v-toolbar>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      title: 'Colombia 19',
      menu: [
        { id: 1, title: "Inicio", link: '/colombia19frontend/' },
        { id: 2, title: "Mercar desde casa", link: '/colombia19frontend/mercados/' },
        { id: 3, title: "Donaciones", link: '/colombia19frontend/donar' }
      ]
    }
  },
 
  methods: {
    menuItems() {
      return this.menu;
    }
  }
}
</script>
<style lang="scss">
header {
  h1 {
    color: #000000;
  }
}
</style>
