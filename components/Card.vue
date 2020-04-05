<template>
    <article class="card">
      <v-card hover>
        <v-list-item three-line>
          <v-list-item-content>
            <div class="overline mb-4">{{ type }}</div>
            <v-list-item-title class="headline mb-1">{{ title }}</v-list-item-title>
            <p>{{ description }}</p>
          </v-list-item-content>
        </v-list-item>

        <v-card-actions>
          <v-btn
            text
          > 
            {{ contact }}
          </v-btn>
        </v-card-actions>
      </v-card>
    </article>
</template>

<script>
export default {
  name: 'Card',
  props: ['title', 'description', 'type', 'contact']
}
</script>

<style lang="scss">

  .card {
    margin: auto;
    padding: 20px 0;
    width: 100%;
  
    @media screen and (min-width: $medium)  {
      width: 600px;
    }
  }
</style>
