<template>
  <ul :style="{ transform: `rotate(${month * -30}deg)` }">
    <li v-for="(item, index) in monthList"
        :key="index"
        :class="{ hover: index == month - 1 }"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script>
  let monthList = [
    "Jan",
    "Feb",
    "Mar",
    "Apr",
    "May",
    "Jun",
    "Jul",
    "Aug",
    "Sep",
    "Oct",
    "Nov",
    "Dec"
  ]
  export default {
    name: 'Month',
    props: {
      month: Number
    },
    data() {
      return {
        monthList: monthList,
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 12 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/12 * 1deg}) translateX(80px);
      }
    }
  }
</style>
