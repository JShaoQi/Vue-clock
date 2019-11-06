<template>
  <ul :style="{ transform: `rotate(${(week + 1) * -51.429}deg)` }">
    <li v-for="(item, index) in weekList"
        :key="index"
        :class="{ hover: index === week }"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script>
  let weekList = [
    "Sun",
    "Mon",
    "Tues",
    "Wed",
    "Thur",
    "Fri",
    "Sat"
  ]
  export default {
    name: 'week',
    props: {
      week: Number
    },
    data () {
      return {
        weekList: weekList
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 7 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/7 * 1deg}) translateX(110px);
      }
    }
  }
</style>
