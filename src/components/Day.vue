<template>
  <ul :style="{ transform: `rotate(${day * -11.613}deg)` }">
    <li v-for="(item, index) in dayList"
        :key="index"
        :class="{ hover: index == day - 1 }"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script>
  let dayList =  [
    "01",
    "02",
    "03",
    "04",
    "05",
    "06",
    "07",
    "08",
    "09",
    "10",
    "11",
    "12",
    "13",
    "14",
    "15",
    "16",
    "17",
    "18",
    "19",
    "20",
    "21",
    "22",
    "23",
    "24",
    "25",
    "26",
    "27",
    "28",
    "29",
    "30",
    "31"
  ]
export default {
  name: 'day',
  props: {
    day: Number
  },
  data () {
    return {
      dayList: dayList,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 31 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/31 * 1deg}) translateX(150px);
      }
    }
  }
</style>
