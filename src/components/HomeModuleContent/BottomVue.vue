<template>
    <div class="homeBottom">
        <div class="day">
            <span class="icon-paste"></span>
            <span>倒数日</span>
        </div>
        <div class="guanli" @click="guanliClick($emit('guanliClick'))">
            <span class="icon-book"></span>
            <span>管理分类</span>
        </div>
        <div class="myInfo">
            <span class="icon-profile"></span>
            <span>我的</span>
        </div>
    </div>
</template>
<script>
export default {
    
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
}
.day,.guanli,.myInfo{
    display: flex;
    flex-direction:column;
    flex-grow: 1;
    box-sizing: border-box;
    align-items: center;
    justify-content: center;
}
.icon-paste,.icon-book,.icon-profile{
    margin-bottom: 0.7vh;
    font-size:3.5vh;
    color: white;
}
</style>