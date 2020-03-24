<template>
  <div class="case">
    <ul>
      <li v-for="item in items" :key="item">
        {{ item.date }}: {{ item.total }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Cases',
  props: ['items']
}
</script>

<style lang="scss"></style>
