<template>
  <div class="detail">
    detail
     <!-- <Calendar
      
      :value="value"
      @next="next"
      @prev="prev"
      @select="select"
      ref="calendar"
      @selectMonth="selectMonth"
      @selectYear="selectYear"
    /> -->
  <div class="" @click="goBack">返回</div>
  </div>
</template>
<script>
import Calendar from 'mpvue-calendar'
import 'mpvue-calendar/src/style.css'
import DateCalendar from 'vuejs-date-calendar'
// import Calendar from 'mpvue-calendar' //
// import 'mpvue-calendar/src/style.css' //引入样式文件(mpvue 小程序端)
export default {
  data() {
    return {
      show:true,
    }
  },
   components: {
    Calendar,
    vDateCalendar:DateCalendar
  },
  methods: {
    goBack(){
      let pages =  getCurrentPages();
      let curPage = pages[pages.length - 1]
      let prevPage = pages[pages.length - 2]
      console.log(prevPage);
      prevPage.data.$root[0].setData('xiaoqu','ddd')
      // prevPage.setData({
      //   '$root[0].nih':'ddd'
      // })
      wx.navigateBack({
        delta: 1
      });
    },
    prev(year, month, weekIndex) {
      console.log(year, month, weekIndex)
    },
    next(year, month, weekIndex) {
      console.log(year, month, weekIndex)
    },
    selectYear(year) {
      console.log(year)
    },
    selectMonth(month, year) {
      console.log(year, month)
    },
    setToday() {
      this.$refs.calendar.setToday()
    },
    dateInfo() {
      const info = this.$refs.calendar.dateInfo(2018, 8, 23)
      console.log(info)
    },
    renderer() {
      this.$refs.calendar.renderer(2018, 8); //渲染2018年8月份
    },
    select(val, val2) {
      console.log(val)
      console.log(val2)
    }
  },
  mounted () {
    // let app = getApp()
    mpvue.setNavigationBarTitle({
      title: '当前页面'
    })
  }
}
</script>
<style>
.detail {
}
</style>