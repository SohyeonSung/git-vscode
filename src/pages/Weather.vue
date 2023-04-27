<template>
  <div id="app">
    <main>
      <div class="weather">
        <div class="location-box">
          <div class="location">Seoul, South Korea</div>
          <div class="date">Friday 27 April 2023</div>
        </div>
        <div class="weather-box">
          <div class="temperture">10℃</div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {};
</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  background-size: cover;
  background-position: bottom;
  background-color: cadetblue;
}
.location-box .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
}
.location-box .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  text-align: center;
}
.weather-box {
  text-align: center;
}
.weather-box .temperture {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 10px;
  margin: 30px 0px;
}
</style>
