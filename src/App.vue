<template>
  <div id="app">
    <date-picker pickertypes="datepicker" :today="computedDate" :value="computedDate" format="DD/MM/YYYY" name="start"></date-picker>
  </div>
</template>

<script>
import DatePicker from './components/datepicker'
import moment from 'moment'
export default {
  computed: {
    computedDate() {
      return moment().format("YYYY-MM-DD")
    }
  },
  components: {
    DatePicker
  },
}
</script>

<style>

</style>
