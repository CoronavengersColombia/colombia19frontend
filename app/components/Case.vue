<template>
  <div class="case">
    <h2>{{ date }}</h2>
    <h3>{{ total }}</h3>
  </div>
</template>

<script>
export default {
  name: 'Case',
  props: ['did', 'date', 'total']
}
</script>

<style lang="scss"></style>
