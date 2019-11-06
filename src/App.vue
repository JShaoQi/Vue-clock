<template>
  <div id="app">
    <v-second :second="second" :class="colors[second%6]"/>
    <v-minute :minute="minute" :class="colors[(second+1)%6]"/>
    <v-hour :hour="hour" :class="colors[(second+2)%6]"/>
    <v-day :day="day" :class="colors[(second+3)%6]"/>
    <v-week :week="week" :class="colors[(second+4)%6]"/>
    <v-month :month="month" :class="colors[(second+5)%6]"/>
    <v-year :year="year"/>
  </div>
</template>
<script>
  import VYear from './components/Year'
  import VMonth from './components/Month'
  import VDay from './components/Day'
  import VWeek from './components/Week'
  import VHour from './components/Hours'
  import VMinute from './components/Minute'
  import VSecond from './components/Second'
  let date = new Date()
  let year = date.getFullYear()
  let month = date.getMonth()
  let week = date.getDate()
  let day = date.getDay()
  let hour = date.getHours()
  let minute = date.getMinutes()
  let second = date.getSeconds()
  let colors = ['red','orange','yellow','green','blue','violet'];
  export default {
    components: {
      VYear,
      VMonth,
      VWeek,
      VDay,
      VHour,
      VMinute,
      VSecond
    },
    data () {
      return {
        year: year,
        month: month+1,
        week: week,
        day: day,
        hour: hour,
        minute: minute,
        second: second,
        colors: colors
      }
    },
    created () {
      this.start();
    },
    methods: {
      start () {
        this.colors = colors;
        setInterval(() => {
          let data = new Date();
          this.second = data.getSeconds();
          this.minute = data.getMinutes();
          this.hour = data.getHours();
          this.week = data.getDay();
          this.day = data.getDate();
          this.month = data.getMonth() + 1;
          this.year = data.getFullYear();
        }, 1000);
      }
    }

  }
</script>
<style lang="scss">
  html,body{
    margin: 0;
  }
#app {
  position: relative;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #000;
  /*color: #2c3e50;*/
  ul {
    list-style-type: none;
    padding: 0;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    height: 20px;
    width: 60px;
    transition: 0.1s 0.1s ease-in;
    li {
      position: absolute;
      height: 20px;
      width: 60px;
      text-align: left;
      font-size: 14px;
      line-height: 20px;
      &.hover {
        color: #fff;
        text-shadow: rgb(255, 255, 255) 0px 0px 10px,
        rgb(255, 255, 255) 0px 0px 20px, rgb(255, 0, 222) 0px 0px 30px,
        rgb(255, 0, 222) 0px 0px 40px, rgb(255, 0, 222) 0px 0px 70px,
        rgb(255, 0, 222) 0px 0px 80px, rgb(255, 0, 222) 0px 0px 100px;
      }
    }
  }
  .red{
    color: #f00;
  }
  .orange{
    color: orange;
  }
  .yellow{
    color: yellow;
  }
  .green{
    color: #0f0;
  }
  .blue{
    color: #00f;
  }
  .violet{
    color: violet;
  }
}
</style>
