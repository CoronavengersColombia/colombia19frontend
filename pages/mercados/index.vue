<template>
  <section>
    <h1>Mercados</h1>
    <Grid :items="stores" />
  </section>
</template>

<script>
import axios from 'axios'
import Grid from '../../components/Grid'

export default {
  components: {
    Grid
  },
  data() {
    return {
      cases: [],
      stores: [
        {
          id: 1,
          title: 'Tienda 1',
          body: 'La tiendita 1',
          contact: '3335566'
        },
        {
          id: 2,
          title: 'Tienda 2',
          body: 'La tiendita 2',
          contact: '333455553'
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
