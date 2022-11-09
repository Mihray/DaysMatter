<template>
    <div class="content">
        <InfoBox></InfoBox>
        <day-list></day-list>
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