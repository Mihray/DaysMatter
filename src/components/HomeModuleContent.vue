<template>
    <div class="content">
        <InfoBox :clickEventlist="ClickEventlist"></InfoBox>
        <day-list :eventList="eventHome" @ShowInfo="showInfo"></day-list>
        <!-- <bottom-vue @guanliClick="guanliClick($emit('guanliClick'))"></bottom-vue> -->
    </div>
</template>

<script>
// import BottomVue from './HomeModuleContent/BottomVue.vue'
import DayList from './HomeModuleContent/DayList.vue'
import InfoBox from './HomeModuleContent/InfoBox.vue'


export default {
  components: { 
    InfoBox,
    DayList,
    // BottomVue ,
}, 
data(){
    return{
        ClickEventlist:{}
    }
}
,
    props:{
        eventHome:Array,
    },
    methods:{
        showInfo(param1){
            console.log('list被点击传来的东西:'+param1)
            this.ClickEventlist=param1;
            console.log('ClickEventlist:'+this.ClickEventlist)
            console.log('ClickEventlist的属性:'+this.ClickEventlist.name)
        },
    }
}
</script>
<style scoped>
.content{
    height:91vh;
    display: flex;
    flex-direction: column;
    /* 水平居中 */
    align-items: center;
    justify-content: space-between;
}
</style>