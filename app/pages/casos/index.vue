<template>
  <section>
    <h1>Proyección de casos por día en Colombia</h1>
    <ul>
      <Case
        v-for="case in cases"
        :key="case.did"
        :did="case.did"
        :date="case.date"
        :total="case.total" />
    </ul>
  </section>
</template>

<script>
import axios from 'axios'
import Case from '../../components/Case'

export default {
  components: {
    Case
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
      }
    }

    try {
      const url = 'http://192.168.0.13:5000/api/cases/'
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
