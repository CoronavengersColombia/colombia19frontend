<template>
  <div class="case">
    <ul>
      <li v-for="item in cases" :key="item">
        {{ item.date }}: {{ item.total }}
      </li>
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
