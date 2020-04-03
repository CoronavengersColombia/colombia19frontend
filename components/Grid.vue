<template>
<v-app>
    <section class="grid">
      <Card v-for="item in items" :key="item.id" :title="item.title" :body="item.body" :contact="item.contact" />
    </section>
  </v-app>
</template>

<script>
import Card from './Card'

export default {
  name: 'Grid',
  props: ['items'],
  components: {
    Card
  }
}
</script>

<style lang="scss">
  .grid {
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
</style>
