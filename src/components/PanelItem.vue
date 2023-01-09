<template>
  <div class="row">
    <h3 class="col-12">Панель {{ panelData.lbl }}</h3>
    <div class="col-12" v-for="(row, key) in panelData.rows" :key="key">
      <RowItem :rowData="row" :formEventBus="formEventBus"></RowItem>
    </div>
  </div>
</template>

<script>
import RowItem from "@/components/RowItem";
export default {
  name: "PanelItem",
  components: {RowItem},
  props: ['panelData', 'formEventBus'],
  created() {
    console.log(this.panelData)
  }
}
</script>

<style scoped>

</style>