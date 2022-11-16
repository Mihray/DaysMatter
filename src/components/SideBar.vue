<template>
    <div class="bigBox">
        <div class="square">
         <div class="arrow" @click="returnHome"> 
             <div class="arrowhead"></div>
             <div class="arrowbody"></div>
         </div>
         <span>倒数日分类</span>
        </div>
        <div class="below"></div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.bigBox{
    width: 80vw;
    height:100vh;
    background-color: white;
    margin-top: -100vh;
    /* 因为Z-index只对定位的元素生效，所以要加position */
    z-index: 1;
    position: absolute;
}
.square{
    /* width:100vmin;
    height:15vmax; */
    width:80vw;
    height:10vh;
    background-color: rgb(53, 162, 189);
    /* position: absolute; */
    display: flex;
}
.arrow{
    display: flex;
    width: 6vh;
    height:5vh ;
    margin-top:5vh ;
    margin-left: 4.5vh;
}
.arrowhead{
    width: 2vh;
    height:2vh ;
    border-width:0 0 0.6vh  0.6vh ;
    border-color:white;
    border-style: solid;
    transform: matrix(0.71, 0.71, -0.71, 0.71, 0, 0);
}
.arrowbody{
    width: 3.5vh;
    height:0.6vh ;
    background-color: white;
    margin-top: 1vh;
    margin-left: -2.4vh;
}
.square span{
    margin-top: 4vh;
    font-size: 3vh;
    color:white
}
</style>