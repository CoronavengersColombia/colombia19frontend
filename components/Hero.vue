<template>
    <v-parallax
    height="300"
    :src="src"
    :alt="alt"
  ></v-parallax>
</template>

<script>
export default {
  name: 'Card',
  props: ['src', 'alt']
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
