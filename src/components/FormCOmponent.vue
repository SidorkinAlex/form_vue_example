<template>
  <div class="form row">
    <h2>Форма</h2>
    <div v-for="(panel, key) in panels" :key="key" :id="key" class="col-12">
      <panel-item :panelData="panel" :formEventBus="formEventBus"></panel-item>
    </div>
    <div class="">
      {{ this.formValues }}
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import PanelItem from "@/components/PanelItem";

export default {
  name: "FormCOmponent",
  components: {PanelItem},
  props:['detail'],
  data(){
    return{
      formValues:{},
      panels:{},
      formEventBus:{},
    }
  },
  created() {
    this.detail.metadata.panels.map(panelItem => {
      Vue.set(this.panels, panelItem.panel_id, panelItem)
    })
    this.formEventBus = this
    console.log(this.panels)
  },
  methods:{
    setFieldValues(fieldName,fieldValue){
      Vue.set(this.formValues, fieldName, fieldValue)
      //this.formValues[fieldName] = fieldValue
    }
  }
}

</script>

<style scoped>
.form{
  background: #eee;
}
</style>