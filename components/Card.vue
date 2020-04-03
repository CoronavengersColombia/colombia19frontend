<template>
    <article class="card">
      <v-card hover>
        <v-card-title>
          {{ title }}
        </v-card-title>    
        <v-card-text>
          <p>{{ title }}</p>
          <b>{{ contact }}</b>
        </v-card-text>
      </v-card>
    </article>
</template>

<script>
export default {
  name: 'Card',
  props: ['title', 'body', 'contact']
}
</script>

<style lang="scss">
  .card {
    margin: auto;
    padding: 20px 0;
    width: 100%;
  
    @media #{$medium-up} {
      width: 600px;
    }
  }
</style>
