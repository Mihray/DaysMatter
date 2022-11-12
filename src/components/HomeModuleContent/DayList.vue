<template>
    <div class="dayList">
        <ul>
            <li v-for="item in eventList" :key="item">{{item.name}}天
                <div>{{item.days}}</div>
            </li>
        </ul>
        <!-- <div v-for="i in eventList" :key="i">
            你好{{i}}
        </div> -->
    </div>
</template>
<script>
export default {
    props:{
            eventList:Array,
         } ,
}
</script>
<style scoped>
.dayList ul{
    list-style: none;
    padding: 0;
}
.dayList ul li{
    width:85vw;
    height: 6vh;
    background-color: white;
    border-radius:4vw;
    display: flex;
    /* 让元素贴右边对齐 */
    justify-content: space-between;
    /* justify-content:center; */
    align-items:center;
    color:rgb(22, 68, 82);
    font-size:3.5vw;
    font-weight:600;
}
.dayList ul li div{
    width:30vw;
    height: 6vh;
    background-color:rgb(53, 162, 189);
    border-radius:0 4vw 4vw 0;
}
</style>