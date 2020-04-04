<template>
  <section>
    <Hero :src="hero.src" :alt="hero.alt" />
    <Grid :items="stores" />
  </section>
</template>

<script>
import axios from 'axios'
import Grid from '../../components/Grid'
import Hero from '../../components/Hero'

export default {
  components: {
    Hero,
    Grid
  },
  data() {
    return {
      cases: [],
      hero: {
        src: '/img/alimentos.jpg',
        alt: 'Mercados'
      },
      stores: [
        {
          title: 'Tienda la 54',
          type: 'Tienda',
          description: 'Frutas, verduras y abarrotes',
          contact: ['3444453', '55762777']
        },
        {
          title: 'Plaza de mercado Chapinero',
          type: 'Plaza',
          description: 'Sólo frutas y verduras',
          contact: ['333455553', '7777777']
        }
      ]
    }
  },
  async created() {
    const config = {
      headers: {
        'Content-Type': 'application/json'
      },
      crossdomain: true
    }

    try {
      const url = 'https://colombia19-api.herokuapp.com/api/cases/'
      const response = await axios.get(url, config)
      this.cases = response.data
    } catch (err) {
      console.log('ERROR:')
      console.log(err)
    }
  },
  head() {
    return {
      title: 'Mercados',
      meta: [
        {
          hid: 'COVID19',
          name: 'covid19',
          content: 'best place'
        }
      ]
    }
  }
}
</script>
<style lang="scss">
header {
  h1 {
    color: blue;
  }
}
</style>
