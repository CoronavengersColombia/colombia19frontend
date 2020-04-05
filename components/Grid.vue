<template>
<v-app>
    <section class="grid">
      <Card 
        v-for="(item, index) in items"
        :key="index"
        :title="item.name"
        :description="item.description"
        :type="item.store_type_description"
        :contact="item.contact" 
      />
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
