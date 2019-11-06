<template>
  <ul>
    <li class="hover">
      {{ year }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'year',
  props: {
    year: Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 1 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/1 * 1deg}) translateX(40px);
      }
    }
  }
</style>
