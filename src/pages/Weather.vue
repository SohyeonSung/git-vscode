<template>
  <div id="WEATHER">
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="오늘의 옷차림 . . 궁금한사람"/>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name:"WEATHER",
  title:"중간고사 과제",
  data(){

  }

}
</script>

<style>
/* SEARCH-BOX 꾸미기 */
main {
  padding: 50px;
}
.search-box {
  width: 100%;
  margin-bottom: 30px;
}
.search-box .search-bar {
  display: block;
  width: 100%;
  padding: 15px;

  font-size: 20px;
  border:none;
  background-color: hsla(228, 3%, 72%, 0.801);
}
</style>
