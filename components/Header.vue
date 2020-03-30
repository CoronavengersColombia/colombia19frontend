<template>
  <header>
    <h1>Colombia 19</h1>
    <ul>
      <li>
        <nuxt-link to="/">Inicio</nuxt-link>
        <nuxt-link to="/casos">Casos</nuxt-link>
        <nuxt-link to="/proyecto">Proyecto</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>
<style lang="scss">
header {
  h1 {
    color: blue;
  }
}
</style>
