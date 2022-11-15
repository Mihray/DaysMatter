<template>

  <HomeModuleTop @addDayBtn="addDayBtn" v-if="homeShow"></HomeModuleTop>
  <HomeModuleContent v-if="homeShow" :eventHome="eventApp"></HomeModuleContent>
  <add-day v-if="addDayShow" @returnHome="returnHome" @subDay="subDayApp" :BookKind="BookKind"></add-day>
  <GuanLiBook v-show="addKind" @returnHome="returnHome" @UpBook="UpBook"></GuanLiBook>
  <bottom-vue @guanliClick="guanliClick"></bottom-vue>
  <!-- <bottom-vue></bottom-vue> -->
</template>

<script>
import HomeModuleTop from './components/HomeModuleTop.vue'
import HomeModuleContent from './components/HomeModuleContent.vue'
import BottomVue from './components/BottomVue.vue'
import AddDay from './components/AddDay.vue'
import GuanLiBook from './components/GuanLiBook.vue'
// import BottomVue from './components/BottomVue.vue'
// import HomeModuleBottom from './components/HomeModuleBottom.vue'


export default {
  name: 'App',
  components: {
    HomeModuleTop,
    HomeModuleContent,
    AddDay,
    GuanLiBook,
    BottomVue,
    // HomeModuleBottom,
  },
  data(){
    return{
            addDayShow:'',
            homeShow:true,
            eventApp:[],
            addKind:'',
            BookKind:[]
    }
  },
  methods:{
    addDayBtn(){
      console.log('传到APPmodule了');
      this.addDayShow=true
      this.homeShow=false
      this.addKind=false
    },
    returnHome(){
      console.log('returnHome触发了')
      this.addDayShow=false
      this.homeShow=true
      this.addKind=false
    },
    subDayApp(param){
      console.log('submitDay触发了')
      const currentEventList = this.eventApp;
      currentEventList.push(param);
      this.eventApp= currentEventList;
      // this.eventApp.push(param)
      console.log('App的event:'+this.eventApp)
      console.log('App的event的name:'+this.eventApp.name)
    },
    guanliClick(){
      this.addKind=true;
      this.homeShow=false;
      this.addDayShow=false;
    },
    UpBook(param4){
      this.BookKind=param4;
      console.log('Book类型是：'+this.BookKind)
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
