<template>
    <div class="dayList">
        <ul :class="{dayListNew:!(TileButVar)}">
            <li v-for="item in eventList" :key="item" @click="ShowInfo($emit('ShowInfo',item))">距{{item.name}}
                <div>{{item.days}}天</div>
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
            TileButVar:Boolean,
         } ,
         data(){
            return{

            }
         },
         methods:{
        
         }
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
    font-size:5vw;
    font-weight:600;
   padding-left: 4vw;
   margin-top: 1vh;
}
.dayList ul li div{
    width:30vw;
    height: 6vh;
    background-color:rgb(53, 162, 189);
    border-radius:0 4vw 4vw 0;
    padding-left: 4vw;
    display: flex;
    justify-content:center;
    align-items:center;
}
.dayList .dayListNew{
    width: 100vw;
    list-style: none;
    padding: 0;
    display: flex;
    margin-top: 11vh;
}
.dayList .dayListNew li{
    padding: 0;
    width:40vw;
    height:15vh;
    background-color: rgb(53, 162, 189);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-left: 6vw;
    box-sizing: border-box;
}
.dayList .dayListNew li div{
    /* width:19vw; */
    height:10vh;
    background-color: rgb(53, 162, 189);
    box-sizing: border-box;
}
</style>