<template>
  <div id="weather">
    <h1>서울 날씨</h1>
    <div v-if= "typeof weather.main != 'undefined'">
      <div :title= "weather.weather[0].main">
      
      </div>
      <div>{{ Math.round(temp) }}℃</div>
    </div>
    <div v-else>
      <div>
      </div>
      <div>
        {{ weather.cod }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      api_key: '3cb5e9d09f5b857f79b7b0def9542649',
      url_base: 'https://api.openweathermap.org/data/2.5/',
      weather: {},
      code: '',
      temp: 0,
     
    }
  },
  mounted() {
    let fetchUrl = `${this.url_base}weather?q=Seoul&units=metric&APPID=${this.api_key}`
    fetch(fetchUrl)
      .then(response => {
        return response.json()
      })
      .then(result => {
        this.weather = result 
        this.temp = result.main.temp 
        this.code = result.weather[0].id.toString() 
      })
  },
}
</script>
 
<style scoped>
#weather {
  font-size: 0.875rem;
  font-weight: 500;
}
</style>