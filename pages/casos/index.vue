<template>
  <section>
    <h1>Proyección de casos por día en Colombia</h1>
    <Cases :cases="cases" />
  </section>
</template>

<script>
import axios from 'axios'
import Cases from '../../components/Cases'

export default {
  components: {
    Cases
  },
  data() {
    return {
      cases: []
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
      title: 'About Colombia19',
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
