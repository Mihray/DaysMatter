<template>
    <div class="infoBox">
        <div class="infoTop">{{clickEventlist.name}}</div>
        <div class="day">{{clickEventlist.days}}<span style="font-size:12vh">天</span></div>
        <div class="date">目标日:{{clickEventlist.date}}</div>
        <!-- <div class="infoTop">你好</div>
        <div class="day">你好<span style="font-size:12vh">天</span></div>
        <div class="date">目标日:</div> -->
    </div>
</template>
<script>
export default {
    props:{
        clickEventlist:Object,
         } ,
}
</script>
<style scoped>
.infoBox{
    width:70vw;
    height:40vh;
    background-color: white;
    /* border:2px solid;
    border-color: black; */
    /* display: flex; */
    margin-top: 12vh;
    border-radius:10vw;
    /* display:felx; */
}
.infoTop{
    width:70vw;
    height:6.7vh;
    background-color:  rgb(53, 162, 189);
    border-radius:10vw 10vw 0 0;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size:3vh ;
    font-weight:700;
    color: white;
    /* flex-grow: 1; */
}
.day{
    width:70vw;
    height:25vh;
    font-size:15vh;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    /* flex-grow: 3; */
    color:rgb(60, 126, 146)
}
.date{
    width:70vw;
    height:6.5vh;
    /* flex-grow: 1; */
    background-color:  rgb(53, 162, 189);
    border-radius:0 0 10vw 10vw ;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size:4vw;
}
</style>