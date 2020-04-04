<template v-slot:activator="{ on }">
  <header>
    <nav>
      <v-toolbar color="indigo" dark fixed>
        <v-toolbar-title>{{ title }}</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn 
            v-for="(item, index) in menuItems"
            :key="index"
            :to="item.link"
            text
          >
            {{ item.title }}
          </v-btn>
        </v-toolbar-items>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-app-bar-nav-icon
              class="hidden-md-and-up"
              v-on="on"
              icon
            ></v-app-bar-nav-icon>
          </template>
          <v-list>
            <v-list-item
              v-for="(item, index) in menuItems"
              :key="index"
              :to="item.link"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data: () => ({
    title: 'Colombia 19',
    menuItems: [
      { id: 1, title: "Inicio", link: '/colombia19frontend/' },
      { id: 2, title: "Mercar desde casa", link: '/colombia19frontend/mercados/' },
      { id: 3, title: "Donaciones", link: '/colombia19frontend/donar' }
    ]
  }),
 
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
