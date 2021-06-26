<template>
  <div class="container row">
    <div class="col-md-8">
      <div class="banner row">
        <div class="banner-text col-md-6">
          <h2>Hello,Friends!</h2>
          <p>Welcome to my website</p>
        </div>
        <div class="col-md-6">
          <img class="banner-img" src="@/static/imgs/mobile.png" alt="laptop png">
        </div>
      </div>
      <div class="show-date mt-5">
        <h4 class="showDate-text">
          Today's Date
        </h4>
        <p class="this-month">
          {{year}} - {{month}}
        </p>
      </div>
      <hr>
      <div class="show-date-card row mx-2 justify-content-between align-center mb-4">
        <div class="d-flex flex-column" v-for="days,index in week" :key="index">
          <div class="text-center date-card" :class="[days.dayNumber==dayNumber? 'today' :'']">
            <p>{{days.dayName}}</p>
            <p>{{days.dayNumber}}</p>
          </div>
        </div>
      </div>
      <hr>
      <div class="reports d-flex justify-content-between">
        <div class="reports-title">
          <h4>Weekly Report</h4>
        </div>
        <div class="report-links">
          <a href="#" :class="{active : activeElem==1}" class="report-link" @click="activeLink(1)">
            Today
          </a>
          <a href="#" :class="{active : activeElem==2}" class="report-link" @click="activeLink(2)">
            Week
          </a>
          <a href="#" :class="{active : activeElem==3}" class="report-link" @click="activeLink(3)">
            Month
          </a>
        </div>
      </div>
      <div class="report-cards row">
        <div class="col-md-3">
          <repot-card icon='music' title="System Junk" color='orange'/>
        </div>
        <div class="col-md-3">
          <repot-card icon='bookmark' title="iTunes Junk" color='red'/>
        </div>
        <div class="col-md-3">
          <repot-card icon='trash-alt' title="System Junk" color='whiteBlue' />
        </div>
        <div class="col-md-3">
          <repot-card icon='photo-video' title="System Junk" color='blue' />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      year:'',
      month:'',
      dayNumber:'',
      week:[],
      activeElem:''
    }
  },
  mounted(){
    const dayName =['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];
    const today = new Date()
    this.day = dayName[today.getDay()];
    this.month = today.toLocaleString('default', { month: 'long' })
    this.year = today.getFullYear()
    this.dayNumber = today.getDate()
    for ( let i=0 ; i<7 ; i++){
      let days = today.getDate() - today.getDay()+i
      const daysObj = {"dayNumber" : `${days}` , 'dayName' : `${dayName[i]}`}
      this.week.push(daysObj)
    }
  },
  methods: {
    activeLink(elem){
      this.activeElem=elem
    }
  },
}
</script>

<style>

</style>
