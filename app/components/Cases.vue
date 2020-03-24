<template>
  <div class="case">
    <h2>{{ cases[0].date }}</h2>
    <ul>
      <li v-for="case in cases" :key="case.did">test</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Cases',
  props: ['cases']
}
</script>

<style lang="scss"></style>
