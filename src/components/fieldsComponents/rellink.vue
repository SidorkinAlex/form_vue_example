<template>
  <div class="row">
    <div class="col-4">{{ fieldData.lbl }}</div>
    <div class="col-8">
      <input type="text" :placeholder="fieldData.name" @input="updateFormFields($event.target.value)">
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "rellink",
  props:["fieldData","formEventBus"],
  methods:{
    updateFormFields(event){
      this.formEventBus.setFieldValues(this.fieldData.name, event)
    }
  },
  created() {
    this.formEventBus.setFieldValues(this.fieldData.name, null)
  }

}
</script>

<style scoped>

</style>