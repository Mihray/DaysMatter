<template>
    <div class="homeBottom">
        <div class="day" @click="dayClikc" :class="{day2:dayClickStyle}">
            <span class="icon-paste"></span>
            <span style="">倒数日</span>
        </div>
        <div class="guanli" @click="guanliClick" :class="{guanli2:dayClickStyle2}">
            <span class="icon-book"></span>
            <span>管理分类</span>
        </div>
        <div class="myInfo" @click="MyClikc" :class="{myInfo2:dayClickStyle3}">
            <span class="icon-profile"></span>
            <span>我的</span>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            dayClickStyle:true,
            dayClickStyle2:false,
            dayClickStyle3:false
        }
    },
    props:{
        homeShow:Boolean
    },
    methods:{
        guanliClick(){
            this.$emit('guanliClick')
            this.dayClickStyle2=true;
            this.dayClickStyle=false;
            this.dayClickStyle3=false;
        },
        dayClikc(){
            this.$emit('dayClikc')
            this.dayClickStyle=true;
            this.dayClickStyle2=false;
            this.dayClickStyle3=false;
        },
        MyClikc(){
            this.$emit('MyClikc')
            this.dayClickStyle3=true;
            this.dayClickStyle2=false;
            this.dayClickStyle=false;
        },
    },
    updated(){
        if(this.homeShow===true){
            console.log('返回到home页面了')
            this.dayClickStyle=true;
            this.dayClickStyle2=false;
            this.dayClickStyle3=false;
        }
    },
}
</script>
<style scoped>
.homeBottom{
    width: 100vw;
    height:9vh;
    background-color:rgb(53, 162, 189);
    display:flex;
    flex-wrap: nowrap;
    box-sizing: border-box;
    bottom: 0;
}
.day,.guanli,.myInfo{
    display: flex;
    flex-direction:column;
    flex-grow: 1;
    box-sizing: border-box;
    align-items: center;
    justify-content: center;
}
.day span,.guanli span,.myInfo span{
    color: white;
}
.icon-paste,.icon-book,.icon-profile{
    margin-bottom: 0.7vh;
    font-size:3.5vh;
    color: white;
}
.guanli2 span{
    color:black;
}
.day2 span{
    color:black;
}
.myInfo2 span{
    color:black;
}
</style>