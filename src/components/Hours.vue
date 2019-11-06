<template>
  <ul :style="{ transform: `rotate(${(hour + 1) * -15}deg)` }">
    <li v-for="(item, index) in hourList"
        :key="index"
        :class="{ hover: index === hour}"
    >
      {{ item }}
    </li>
  </ul>
</template>

<script>
  let hourList =  [
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
  ]
  export default {
    name: 'hours',
    props: {
      hour: Number
    },
    data() {
      return {
        hourList: hourList,
        rotates: 0
      }
    }
    // watch: {
    //   hour (val) {
    //     this.rotates = val;
    //   }
    // }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ul {
    z-index: 5;
    @for $i from 1 through 24 {
      li:nth-child(#{$i}) {
        transform: rotate(#{$i * 360/24 * 1deg}) translateX(180px);
      }
    }
  }
</style>
