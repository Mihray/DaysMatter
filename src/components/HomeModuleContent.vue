<template>
    <div class="content">
        <InfoBox :eventBox="eventHome"></InfoBox>
        <day-list :eventList="eventHome"></day-list>
    </div>
</template>

<script>
import DayList from './HomeModuleContent/DayList.vue'
import InfoBox from './HomeModuleContent/InfoBox.vue'


export default {
  components: { 
    InfoBox,
    DayList ,
}, 

    props:{
        eventHome:Array,
    } ,
}
</script>
<style scoped>
.content{
    display: flex;
    flex-direction: column;
    /* 水平居中 */
    align-items: center;
}
</style>