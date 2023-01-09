<template>
  <div class="row">
    <template v-if="rowData.length>1">
      <div class="col-lg-6">
        <component
            :is="rowData[0].type + 'Component'"
            :fieldData="rowData[0]"
            :formEventBus="formEventBus"
        ></component>
      </div>
      <div class="col-lg-6">
        <component
            :is="rowData[1].type + 'Component'"
            :fieldData="rowData[1]"
            :formEventBus="formEventBus"
        ></component>
      </div>
    </template>
    <template  v-if="rowData.length === 1">
      <div class="col-lg-12">
        <component
            :is="rowData[0].type + 'Component'"
            :fieldData="rowData[0]"
            :formEventBus="formEventBus"
        ></component>
      </div>
    </template>
  </div>
</template>

<script>
import dateComponent from '@/components/fieldsComponents/date'
import datetimeComponent from '@/components/fieldsComponents/datetime'
import enumComponent from '@/components/fieldsComponents/enum'
import imageComponent from '@/components/fieldsComponents/image'
import MeansCommunicationComponent from '@/components/fieldsComponents/MeansCommunication'
import multienumComponent from '@/components/fieldsComponents/multienum'
import relateComponent from '@/components/fieldsComponents/relate'
import rellinkComponent from '@/components/fieldsComponents/rellink'
import varcharComponent from '@/components/fieldsComponents/varchar'
export default {
  name: "RowItem",
  props:['rowData','formEventBus'],
  components: {
    dateComponent,
    datetimeComponent,
    enumComponent,
    imageComponent,
    MeansCommunicationComponent,
    multienumComponent,
    relateComponent,
    rellinkComponent,
    varcharComponent,
  },
  created() {
    console.log(this.rowData.length)
  }
}
</script>

<style scoped>

</style>