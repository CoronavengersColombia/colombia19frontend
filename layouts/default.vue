<template>
  <v-app>
    <div class="wrapper">
      <Header />
      <nuxt />
    </div>
  </v-app>
</template>
<script>
import Header from '../components/Header'

export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
  .wrapper {
    height: 100%;
    margin: 0;
    padding: 0;
    width: 100%;
  }
</style>
