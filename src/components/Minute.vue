<template>
  <ul :style="{ transform: `rotate(${(minute + 1) * -6}deg)` }">
    <li v-for="(item, index) in minuteList"
        :key="index"
        :class="{ hover: index == minute}"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script>
  let minuteList = [
    "00",
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
    "31",
    "32",
    "33",
    "34",
    "35",
    "36",
    "37",
    "38",
    "39",
    "40",
    "41",
    "42",
    "43",
    "44",
    "45",
    "46",
    "47",
    "48",
    "49",
    "50",
    "51",
    "52",
    "53",
    "54",
    "55",
    "56",
    "57",
    "58",
    "59"
  ]
  export default {
    name: 'minute',
    props: {
      minute: Number
    },
    data () {
      return {
        minuteList: minuteList,
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 60 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/60 * 1deg}) translateX(200px);
      }
    }
  }
</style>
