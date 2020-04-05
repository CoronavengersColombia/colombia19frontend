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
      hero: {
        src: './img/alimentos.jpg',
        alt: 'Mercados'
      },
      stores: []
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
      const url = 'https://colombia19-api.herokuapp.com/api/stores/'
      const response = await axios.get(url, config)
      this.stores = response.data
      console.log(response)
      window.cosito = response
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
