<template>
  <HomeModuleTop @addDayBtn="addDayBtn" v-if="homeShow"></HomeModuleTop>
  <HomeModuleContent v-if="homeShow" :eventHome="eventApp"></HomeModuleContent>
  <add-day v-if="addDayShow" @returnHome="returnHome" @subDay="subDayApp"></add-day>
  <!-- <HomeModuleBottom></HomeModuleBottom> -->
</template>

<script>
import HomeModuleTop from './components/HomeModuleTop.vue'
import HomeModuleContent from './components/HomeModuleContent.vue'
import AddDay from './components/AddDay.vue'
// import HomeModuleBottom from './components/HomeModuleBottom.vue'


export default {
  name: 'App',
  components: {
    HomeModuleTop,
    HomeModuleContent,
    AddDay,
    // HomeModuleBottom,
  },
  data(){
    return{
            addDayShow:'',
            homeShow:true,
            eventApp:[],
    }
  },
  methods:{
    addDayBtn(){
      console.log('传到APPmodule了');
      this.addDayShow=true
      this.homeShow=false
    },
    returnHome(){
      console.log('returnHome触发了')
      this.addDayShow=false
      this.homeShow=true
    },
    subDayApp(param){
      console.log('submitDay触发了')
      const currentEventList = this.eventApp;
      currentEventList.push(param);
      this.eventApp= currentEventList;
      // this.eventApp.push(param)
      console.log('App的event:'+this.eventApp)
      console.log('App的event的name:'+this.eventApp.name)
    }
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50; */
  /* margin-top: 60px; */
  font-size: 14px;
}
body{
  background-color: rgb(131, 222, 225);
  margin: 0;
  padding: 0;
}
</style>
