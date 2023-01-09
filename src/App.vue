<template>
  <div id="app" class="container">
    <h1>Приложение</h1>
    <div class="app-form-example">
      <FormCOmponent :detail="FormData"/>
    </div>
  </div>
</template>

<script>
import Detail from "./mock/detail.json"
import FormCOmponent from "@/components/FormCOmponent";

export default {
  name: 'App',
  components: {
    FormCOmponent,
  },
  computed:{
    FormData(){
      return Detail
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
