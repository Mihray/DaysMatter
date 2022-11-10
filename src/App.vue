<template>
  <HomeModuleTop @addDayBtn="addDayBtn" v-if="homeShow"></HomeModuleTop>
  <HomeModuleContent v-if="homeShow"></HomeModuleContent>
  <add-day v-if="addDayShow"></add-day>
</template>

<script>
import HomeModuleTop from './components/HomeModuleTop.vue'
import HomeModuleContent from './components/HomeModuleContent.vue'
import AddDay from './components/AddDay.vue'


export default {
  name: 'App',
  components: {
    HomeModuleTop,
    HomeModuleContent,
    AddDay
  },
  data(){
    return{
            addDayShow:'',
            homeShow:true,
    }
  },
  methods:{
    addDayBtn(){
      console.log('传到APPmodule了');
      this.addDayShow=true
      this.homeShow=false
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
