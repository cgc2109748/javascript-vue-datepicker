<style media="screen">
  .datepicker-container {
    position: relative;
  }
</style>

<template>
  <div class="datepicker-container ui input action">
    <div class="ui action input">
      <input type="text" value="{{ date_formatted }}">
      <button class="ui icon button" @click="showDatepicker" >
        <i class="calendar icon"></i>
      </button>
    <div>
    <!-- <input type="text" value="{{ date_formatted }}" @click="showDatepicker"> -->
    <input type="hidden" name="{{ name }}" value="{{ date_raw }}">
    <datepicker-agenda :ttoday="ttoday" :date="date" :visible="isVisible" @change="selectDate" @cancel="hideDatepicker"></datepicker-agenda>
  </div>
</template>

<script>
import moment from 'moment'
import DatepickerAgendaComponent from './DatepickerAgenda.vue'

moment.locale('zh-cn');

export default {
  components: {
    'datepicker-agenda': DatepickerAgendaComponent
  },
  props: {
    value: {
      type: String,
      required: true
    },
    format: {
      type: String,
      default: 'YYYY-MM-DD'
    },
    name: {
      type: String
    },
    pickertypes: {
      type: String
    },
    today: {
      type: String
    }
  },
  computed: {
    date_formatted: function() {
      return this.date.format(this.format)
    },
    date_raw: function() {
      return this.date.format('YYYY-MM-DD')
    }
  },
  methods: {
    selectDate: function(date) {
      this.date = date
      this.hideDatepicker()
    },
    showDatepicker: function() {
      this.isVisible = true
      setTimeout(() => document.addEventListener('click',this.hideDatepicker),0)
    },
    hideDatepicker: function() {
      this.isVisible = false
        document.removeEventListener('click',this.hideDatepicker)
    }
  },
  data: function() {
    return {
      isVisible: false,
      pickertype:this.pickertypes,
      ttoday: moment(this.today,'YYYY-MM-DD'),
      date: moment(this.value,'YYYY-MM-DD')
    }
  }
}

</script>
