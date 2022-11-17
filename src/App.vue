<template>

  <HomeModuleTop   @addDayBtn="addDayBtn" v-if="homeShow" @menulineClick="menulineClick"></HomeModuleTop>
  <HomeModuleContent  v-if="homeShow" :eventHome="eventApp"></HomeModuleContent>
  <add-day v-if="addDayShow" @returnHome="returnHome" @subDay="subDayApp" :BookKind="BookKind"></add-day>
  <GuanLiBook v-show="addKind" @returnHome="returnHome" @UpBook="UpBook"></GuanLiBook>
  <MyInfo v-if="myInfoShow"></MyInfo>
  <bottom-vue  @guanliClick="guanliClick" @dayClikc="dayClikc" @MyClikc="MyClikc"></bottom-vue>
  <home-opacity v-if="isHomeOpacity"></home-opacity>
  <side-bar v-if="SideBarShow" :BookKind2="BookKind" :close="closeSidebar" :allAmount="allAmount" :lifeAmount="lifeAmount" :workAmount="workAmount" :memorialDayAmount="memorialDayAmount"></side-bar>
  <!-- <bottom-vue></bottom-vue> -->
</template>

<script>
import HomeModuleTop from './components/HomeModuleTop.vue'
import HomeModuleContent from './components/HomeModuleContent.vue'
import BottomVue from './components/BottomVue.vue'
import AddDay from './components/AddDay.vue'
import GuanLiBook from './components/GuanLiBook.vue'
import MyInfo from './components/MyInfo.vue'
import SideBar from './components/SideBar.vue'
import HomeOpacity from './components/HomeOpacity.vue'


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
    MyInfo,
    SideBar,
    HomeOpacity,
},
  data(){
    return{
            addDayShow:'',
            homeShow:true,
            eventApp:[],
            addKind:'',
            BookKind:[],
            myInfoShow:'',
            SideBarShow:'',
            // BottomShow:true
            isHomeOpacity:false,
            allAmount:0,
            lifeAmount:0,
            workAmount:0,
            memorialDayAmount:0
    }
  },
  methods:{
    addDayBtn(){
      console.log('传到APPmodule了');
      this.addDayShow=true
      this.homeShow=false
      this.addKind=false
      this.myInfoShow=false
      this.SideBarShow=false
    },
    returnHome(){
      console.log('returnHome触发了')
      this.addDayShow=false
      this.homeShow=true
      this.addKind=false
      this.myInfoShow=false
      this.SideBarShow=false
    },
    subDayApp(param){
      console.log('submitDay触发了')
      const currentEventList = this.eventApp;
      currentEventList.push(param);
      this.eventApp= currentEventList;
      // this.eventApp.push(param)
      console.log('App的event:'+this.eventApp)
      console.log('App的event的name:'+this.eventApp.name)
      this.allAmount++
      console.log('全部事件数目：'+this.allAmount)
      if(param.kindVar==='生活'){
        this.lifeAmount++;
        console.log('生活类型：'+this.lifeAmount)
      }
      if(param.kindVar==='工作'){
        this.workAmount++;
        console.log('工作类型：'+this.workAmount)
      }
      if(param.kindVar==='纪念日'){
        this.memorialDayAmount++;
        console.log('纪念日：'+this.memorialDayAmount)
      }
    },
    guanliClick(){
      this.addKind=true;
      this.homeShow=false;
      this.addDayShow=false;
      this.myInfoShow=false
      this.SideBarShow=false
    },
    UpBook(param4){
      this.BookKind=param4;
      console.log('Book类型是：'+this.BookKind)
    },
    dayClikc(){
      this.addKind=false;
      this.homeShow=true;
      this.addDayShow=false;
      this.myInfoShow=false
      this.SideBarShow=false
    },
    MyClikc(){
      this.addKind=false;
      this.homeShow=false;
      this.addDayShow=false;
      this.myInfoShow=true;
      this.SideBarShow=false
    },
    menulineClick(){
      this.addKind=false;
      this.homeShow=true;
      this.addDayShow=false;
      this.myInfoShow=false
      this.SideBarShow=true
      // this.BottomShow=false
      this.isHomeOpacity=true;
    },
    closeSidebar(){
      this.SideBarShow = false;
      this.addKind=false;
      this.homeShow=true;
      this.addDayShow=false;
      this.myInfoShow=false
      this.isHomeOpacity=false;
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
/* .HomeOpacity{
  width: 100vw;
  height: 109vh;
  background-color: black;
  opacity: 0.4;
  position: absolute;
  z-index: 1;
  position: absolute;
} */
</style>
