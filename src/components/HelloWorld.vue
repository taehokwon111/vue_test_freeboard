<template>
 <div id="clock">
    <p>날짜</p> {{ date }}
    <br />
    <p>시간</p> {{ time }}
  </div>
</template>

<script>
export default {
data() {
  return{
  week: ['SUN', "MON", "TUE", "WED", "THU", "FRI", "SAT"],
  time: '',
  date: ''
}
},
mounted() {
  setInterval(this.updateTime, 1000)
},
methods: {
   updateTime() {
      var cd = new Date()
      this.date =
        this.zeroPadding(cd.getFullYear(), 4) +
        '/' +
        this.zeroPadding(cd.getMonth() + 1, 2) +
        '/' +
        this.zeroPadding(cd.getDate(), 2) +
        ' ' +
        this.week[cd.getDay()]
      this.time =
        this.zeroPadding(cd.getHours(), 2) +
        ':' +
        this.zeroPadding(cd.getMinutes(), 2) +
        ':' +
        this.zeroPadding(cd.getSeconds(), 2)
    },
    zeroPadding(num, digit){
      var zero = ''
      for(let i = 0; i < digit; i++){
        zero += '0'
      }
      return (zero + num).slice(-digit)
    }
},
}
</script>

<style scoped>

</style>
