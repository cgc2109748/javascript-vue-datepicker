<style lang="scss">
$header_height:100px;
$day-size:41px;

.datepicker{
position: absolute;
top: 100%;
left: 0;
width: 315px;
z-index: 5;
background-color: #fff;
border-radius: 5px;
box-shadow: 0 14px 45px rgba(0,0,0,0.25), 0 10px 18px rgba(0,0,0,0.22);
}

.datepicker_header {
background-color: #5ac4f4;
color: #FFF;
padding: 20px;
height: $header_height;
border-radius: 5px 5px 0 0;
}

.datepicker_year {
position: relative;
overflow: hidden;
height: 16px;
opacity: 0.7;
margin-bottom: 10px;
line-height: 16px;
}

.datepicker_date {
position: relative;
overflow: hidden;
height: 32px;
font-size: 32px;
line-height: 32px;
}

.datepicker_week{
font-size: 12px;
line-height: 12px;
color: rgba(0,0,0,0.8);
padding: 0 14px;
}

.datepicker_weekday {
float: left;
width: $day-size;
text-align: center;
}

.datepicker_days {
position: relative;
overflow: hidden;
margin: 14px;
height: $day-size * 5;
transition: height 0.3s;
&.has-6-weeks {
  height: $day-size * 6;
}
}

.datepicker_day {
position: relative;
width: $day-size;
height: $day-size;
float: left;
text-align: center;
line-height: $day-size;
cursor: pointer;
-webkit-transition: color 450ms cubic-bezier(0.23, 1, 0.32, 1) 0ms;
transition: color 450ms cubic-bezier(0.23, 1, 0.32, 1) 0ms;
border-bottom: 1px solid #e3e3e3;
}

.datepicker_day_effect {
position: absolute;
top: 2px;
left: 2px;
width: 36px;
height: 40px;
// border-radius: 50%;
background-color: #edf6fc;
-webkit-transition: transform 450ms cubic-bezier(0.23, 1, 0.32, 1) 0ms;
transition: transform 450ms cubic-bezier(0.23, 1, 0.32, 1) 0ms;
-webkit-transform: scale(0);
transform: scale(0);
opacity: 0;
}

.datepicker_day_text {
position: relative;
}

.datepicker_day:hover {
// color: #FFF;
.datepicker_day_effect {
  transform: scale(1);
  opacity: 0.7;
  border-bottom:5px solid #5ac4f4;
}
}

.datepicker_day.selected {
// color: #FFF;
.datepicker_day_effect {
  transform: scale(1);
  opacity: 1;
  border-bottom:5px solid #5ac4f4;
}
}

.datepicker_day.today {
.datepicker_day_corner {
  position: absolute;
  bottom:-2px;
  right: 3px;
  margin: 0;
  padding: 0;
  z-index: 10;
  border-bottom: 10px solid #fc7d7d;
  border-left: 10px solid transparent;
}
}

.datepicker_controls {
position: relative;
height: 56px;
line-height: 56px;
text-align: center;

button {
  position: relative;
  border: none;
  background-color: transparent;
  user-select:none;
  outline:none;
  cursor: pointer;
  width: 56px;
  height: 56px;
}

svg {
  width: 24px;
  height: 24px;
  fill:rgba(0,0,0,0.87);
  vertical-align: middle;
}
}

.datepicker_month {
  position: absolute;
  width: 245px;
  height: 25px;
  border-radius: 3px;
  line-height: 25px;
  overflow: hidden;
  top: 17px;
  left: 35px;
  right: 0;
  bottom: 0;
  cursor: pointer;
  span:hover {
    transition: all 0.3s;
    background-color: #edf6fc;
  }
}

.datepicker_next {
  float: right;
  background-color: transparent;
  svg:hover {
    border-radius: 3px;
    transition: all 0.3s;
    background-color: #edf6fc;
  }
}

.datepicker_prev {
  float: left;
  background-color: transparent;
  svg:hover {
    border-radius: 3px;
    transition: all 0.3s;
    background-color: #edf6fc;
  }
}

.datepicker_actions {
  border-top: 2px solid #e1e1e1;
  text-align: left;;
  padding: 8px;

}

.datepicker_actions button {
  padding: 6px !important;
  border: none;
  background-color: transparent;
  display: inline-block;
  cursor: pointer;
  outline: none;
  color: #00bcd4;
  font-size: 14px;
  text-transform: uppercase;
  font-weight: 500;
  min-width: 68px;
  line-height: 36px;
  text-align: center;
  -webkit-apparance:none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  &:hover{
    background-color: rgba(153,153,153,0.2)
  }
}

.datepicker-slide-transition {
  opacity: 1;
  transition: all 0.3s;
  transform: translateY(0);
}

.datepicker-slide-leave,
.datepicker-slide-enter {
  opacity: 0;
  transform: translateY(-15px);
}

.pickers {
  position: relative;
  height: 200px;
  transition: height 0.3s;
}

.pickers button {
  position: absolute;
  bottom: 10px;
  left:39%;
}

.pickers_year {
  position: absolute;
  left: 0;
  top:20px;
  width: 50%;

  .pickers_year_text {
    display: block;
    text-align: center !important;
    font-size: 24px;
  }
  .year_prev {
    text-align: center;
    font-size: 20px;
    border-radius: 5px;
  }
  .year_prev:hover {
    cursor: pointer;
    transition: all 0.3s;
  }
  .year_next {
    text-align: center;
    font-size: 20px;
    border-radius: 5px;
  }
  .year_next:hover {
    cursor: pointer;
    transition: all 0.3s;
  }
}

.pickers_month {
  position: absolute;
  right: 0;
  top: 20px;
  width: 50%;

  .pickers_month_text {
    display: block;
    text-align: center !important;
    font-size: 24px;
  }
  .month_prev {
    text-align: center;
    font-size: 20px;
    border-radius: 5px;
  }
  .month_prev:hover {
    cursor: pointer;
    transition: all 0.3s;
  }
  .month_next {
    text-align: center;
    font-size: 20px;
    border-radius: 5px;
  }
  .month_next:hover {
    cursor: pointer;
    transition: all 0.3s;
  }
}

.datepicker_wrapper {
  transition: height 0.3s;
  overflow: hidden;
}

.datepicker_wrapper.has-5-weeks {
  height: 333px;
}

.datepicker_wrapper.has-6-weeks {
  height: 374px;
}

.datepicker_wrapper.pickers-wrapper {
  height: 200px;
}


.slidev-transition {
position: absolute;
top: 0;
right: 0;
bottom: 0;
left: 0;
transition: all 0.3s;
transform: translateX(0);
opacity: 1;
&.off{
  transition-duration: 0s;
}
}

.slidev-leave, .direction-prev.slidev-enter {
transform: translateX(-100%);
opacity: 0;
}

.slidev-enter, .direction-prev.slidev-leave {
transform: translateX(100%);
opacity: 0;
}



.slideh-transition {
position: absolute;
top: 0;
right: 0;
bottom: 0;
left: 0;
transition: all 0.3s;
transform: translateX(0);
opacity: 1;
&.off{
  transition-duration: 0s;
}
}

.slideh-leave, .direction-prev.slideh-enter {
transform: translateY(-100%);
opacity: 0;
}

.slideh-enter, .direction-prev.slideh-leave {
transform: translateY(100%);
opacity: 0;
}

</style>

<template>
  <div class="datepicker" v-if="visible" transition="datepicker-slide" @click.stop>
    <div class="datepicker_header">
      <div class="datepicker_year">
        <span v-for="year in [year]" transition="slideh" :class="dayDirection">{{ year }}</span>
      </div>
      <div class="datepicker_date">
        <span v-for="date_formatted in [date_formatted]" transition="slideh" :class="dayDirection">{{ date_formatted }}</span>
      </div>
    </div>

    <div class="datepicker_wrapper" transition="slidew" :class="classWeeks">
      <div v-if="datepicker">
        <div class="datepicker_controls">
          <div class="datepicker_month">
            <span v-for="month in [month]" @click="showPicker" transition="slideh" :class="classDirection">{{ month.getFormatted() }}</span>
          </div>
          <button class="datepicker_next" @click="nextMonth()">
            <svg viewBox="0 0 24 24"><path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"></path></svg>
          </button>
          <button class="datepicker_prev" @click="prevMonth()">
            <svg viewBox="0 0 24 24"><path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z"></path> </svg>
          </button>
        </div>
          <div class="datepicker_week">
            <div v-for="day in days" track-by="$index" class="datepicker_weekday">
              {{ day }}
            </div>
          </div>
          <div class="datepicker_days" :class="classWeeks">
            <div v-for="month in [month]" transition="slidev" :class="classDirection">
              <div class="datepicker_day" :style="{ width:(month.getWeekStart() * 41) + 'px' }">
              </div>
              <div class="datepicker_day" @click="selectDate(day)" v-for="day in month.getDays()" :class="{ selected: isSelected(day), 'today': isToday(day) }">
                <span class="datepicker_day_corner"></span>
                <span class="datepicker_day_effect"></span>
                <span class="datepicker_day_text">{{ day.format('D') }}</span>
              </div>
            </div>
          </div>
        <div class="datepicker_actions">
          <button class="ui button" @click="selectToday"><i class="wait icon"></i> 今天 </button>
          <button class="ui button"><i class="trash icon"></i> 清空 </button>
          <button class="ui button" @click="submit">确定</button>
          <button class="ui button" @click="cancel">取消</button>
        </div>
      </div>
      <div class="pickers" v-if="pickers">
        <div class="pickers_year">
          <div class="year_next" @click="nextYear"><i class="chevron up icon"></i></div>
          <input class="pickers_year_text" v-for="year in [month]" value="{{ month.getYear() }}" v-model="inputYear"  @change="picker_changeMonth(inputYear,inputMonth)">
          <div class="year_prev" @click="prevYear"><i class="chevron down icon"></i></div>
        </div>
        <div class="pickers_month">
          <div class="month_next" @click="picker_nextMonth"><i class="chevron up icon"></i></div>
          <input class="pickers_month_text" v-for="month in [month]" value="{{ month.getMonthInNumber() }}"  v-model="inputMonth" @change="picker_changeMonth(inputYear,inputMonth)">
          <div class="month_prev" @click="picker_prevMonth"><i class="chevron down icon"></i></div>
        </div>
        <button class="ui button" @click="hidePicker">确定</button>
      </div>
    </div>
  </div>
</template>


<script>
import moment from 'moment'
import Month from './modules/month'
import cx from 'classnames'

moment().format()

export default {
  props: {
    date: {

    },
    ttoday: {

    },
    pickertype: {
      type:String
    },
    visible: {
      type: Boolean,
      default: true
    },
    inputYear: {
      type: Number
    },
    inputMonth: {
      type: Number
    }
  },
  data() {
    return {
      days: ['日','一','二','三','四','五','六'],
      month: new Month(this.date.month(),this.date.year()),
      classDirection: 'off',
      dayDirection: 'off',
      pickerWrapper: false,
      datepicker:true,
      pickers:false
    }
  },
  methods: {
    isSelected: function(day) {
      // debugger
      return this.date.unix() === day.unix()
    },
    isToday: function(day) {
      // debugger
      return this.today.format('YYYY-MM-DD') == day.format('YYYY-MM-DD')
    },
    selectDate: function(day) {
      this.dayDirection = 'direction-next'
      if(day.isBefore(this.date)) {
          this.dayDirection = 'direction-prev'
      }
      this.date = day.clone()
      // this.$dispatch('change', this.date)
    },
    selectToday: function() {
      if(this.today.month() == this.month.month && this.today.year() == this.month.year) {
        document.getElementsByClassName('today')[0].click()
      }
      else {
        let month = this.today.month()
        let year = this.today.year()
        this.month = new Month(month,year)
        setTimeout(() => document.getElementsByClassName('today')[0].click(),0.3)
      }
    },
    nextMonth: function() {
      this.classDirection = 'direction-next'
      let month = this.month.month + 1
      let year = this.month.year
      if (month > 11){
        year += 1
        month = 0
      }
      this.month = new Month(month,year)
    },
    prevMonth: function() {
      this.classDirection = 'direction-prev'
      let month = this.month.month - 1
      let year = this.month.year
      if (month < 0){
        year -= 1
        month = 11
      }
      this.month = new Month(month,year)
    },
    nextYear: function() {
      let month = this.month.month
      let year = this.month.year + 1
      if(year > 2999) {
        year = 2999
      }
      this.month = new Month(month,year)
    },
    prevYear: function() {
      let month = this.month.month
      let year = this.month.year - 1
      if (year < 1949){
        year = 1949
      }
      this.month = new Month(month,year)
    },
    picker_nextMonth: function() {
      let month = this.month.month + 1
      let year = this.month.year
      if (month > 11){
        month = 11
      }
      this.month = new Month(month,year)
    },
    picker_prevMonth: function() {
      let month = this.month.month - 1
      let year = this.month.year
      if (month < 0){
        month = 0
      }
      this.month = new Month(month,year)
    },
    picker_changeMonth: function(inputYear,inputMonth) {
      let month = Number(inputMonth) - 1
      let year = Number(inputYear)
      this.month = new Month(month,year)
    },
    submit: function() {
      this.$dispatch('change', this.date)
    },
    cancel: function() {
      this.$dispatch('cancel')
    },
    showPicker: function() {
      this.datepicker = false
      this.pickers = true
      this.pickerWrapper = true
    },
    hidePicker: function() {
      this.pickerWrapper = false
      this.datepicker = true
      this.pickers = false
    }
  },
  watch: {
    visible: function(val, oldVal) {
      if(val === false) {
        this.classDirection = 'off'
        this.dayDirection = 'off'
      }
    }
  },
  computed: {
    year() {
      return this.date.format('YYYY')
    },
    classWeeks() {
      // return 'has-' + this.month.getWeeks() + '-weeks'
      return cx({
        [`has-${this.month.getWeeks()}-weeks`]: 1,
        ['pickers-wrapper']: this.pickerWrapper
      })
    },
    date_formatted() {
      return this.date.format('dddd DD MMMM')
    },
    today() {
      return this.ttoday
    }
  }
}

</script>
