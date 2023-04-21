<template>
  <q-card-section class="row text-center">
    <q-card-section class="col text-h4 text-primary">
      {{  header || "welCome" }}
    </q-card-section>
  </q-card-section>
</template>

<script>
export default {
  name:"WEATHER",
  title:"중간고사 과제",
  data(){
    return {
      header:"Today's weather~"
    }
  }

}
</script>

<style>

</style>
