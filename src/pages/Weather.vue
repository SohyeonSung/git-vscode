<template>
   <div id="app">
    <main>
      <div class="weather">
        <div class="location-box">
          <div class="location">Seoul, South Korea</div>
          <div class="date">Tuesday 2 May 2023</div>
        </div>
        <div class="weather-box">
          <div class="temperture">10℃</div>
        </div>
      </div>
    </main>
  </div>

  <q-card-section class="row text-center">
    <q-card-section class="col text-h4 text-primary">
      {{  header || "" }}
      <!--add item or modi-->
      <q-btn
        v-if="editing"
        @click="doEdit(false)"
        color="primary"
            unelevated
            rounded
            label="CANCEL"
      ></q-btn>
      <q-btn
      v-else
      @click="doEdit(true)"
      color="primary"
            unelevated
            rounded
            label="SHARE"
      ></q-btn>
    </q-card-section>
  </q-card-section>

  <!--item add-->
  <q-card-section class="row justify-center">
    <q-card-section v-if="editing" class="col-8 col-md-3">
      <q-input
        v-model="newItem"
        @keyup.enter="saveItem"
        label="글 작성"
      ></q-input>
    </q-card-section>

    <!--saveItem-->
     <q-card-section v-if="editing" class="col-12 col-md-3">
      <q-btn outline rounded color="primary" @click="saveItem()" label="글 저장"></q-btn>
    </q-card-section>
  </q-card-section>

  <!--list-->
  <q-card-section>
    <q-list bordered>
      <q-item
        v-for="item in reversedItems"
        :key="item.id"
        @click="togglePurchased(item)"
        class="rounded-border"
        :class="{strikeout:item.purchased, priority:item.highPriority}"
        dense
        padding
        clickable
        v-ripple>

        <q-item-section>
          {{ item.label }}
        </q-item-section>
      </q-item>
    </q-list>
  </q-card-section>

  <!--notify-->
  <q-item-section class="row text-center">
        <q-card-section>
          <span v-if="items.length === 0"
            > 당신의 옷차림을 공유해주세요!</span>
        </q-card-section>
  </q-item-section>
</template>

<script>
export default {
  name:"",
  title:"Weather",
  data(){
    return {
      header:"",
      items : [
        // { id: 1, label: "10 party hats", purchased: true, highPriority: false },
        // { id: 2, label: "2 board games", purchased: true, highPriority: false },
        // { id: 3, label: "20 cups", purchased: false, highPriority: true },
      ],
      editing:false,
      newItem:"",
      newItemHighPriority:false,
    }
  },
  computed : {
    reversedItems(){
      return [...this.items].reverse();
    }
  },
  methods :{
    togglePurchased(item){
      item.purchased = !item.purchased;
    },
    doEdit(editing){
      this.editing = editing;
      this.newItem = "";
      this.newItemHighPriority = false;
    },
    async saveItem(){
      if(this.newItem.length == 0) return;
      this.items.push({
        id: this.items.length + 1,
        label: this.newItem,
        highPriority: this.newItemHighPriority,
      });

      this.newItem = "";
      this.newItemHighPriority =false;
    }
  }

}
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
}
.location-box .location {
  color:steelblue;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
}
.location-box .date {
  color: steelblue;
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
  color: white;
  font-size: 102px;
  font-weight: 900;
  background-color: steelblue;
  border-radius: 10px;
  margin: 30px 0px;
}

</style>
