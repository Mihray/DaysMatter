<template>
    <!-- <link rel="stylesheet" href="../assets/icomoon/style.css"> -->
    <div class="square">
        <div class="arrow"> 
            <div class="arrowhead"></div>
            <div class="arrowbody"></div>
        </div>
        <span>添加新倒数日</span>
    </div>
    <div class="inputBox">
        <div class="eventName">
            <span class="icon-paste"></span>
            <input   placeholder="输入事件名称">
        </div>
        <div class="date"> 
            <span class="icon-calendar"></span> 
            <input type="date"   placeholder="目标日">
        </div>
        <div class="kind"> 
            <span class="icon-book"></span> 
            <div>倒数本
                <select id="kindInput">
                    <option>生活</option>
                    <option>工作</option>
                    <option>纪念日</option>
                </select>
            </div>
        </div>
        <div class="overHead"> 
            <span class="icon-upload"></span>
            <div>顶置
                <div class="switch"> 
                    <div class="down"></div>
                    <div class="circle"></div>
                </div>
            </div>
        </div>
        <div class="repitition"> 
            <span class="icon-spinner11"></span>
            <div>重复
                <select>
                    <option>不重复</option>
                    <option>每周</option>
                    <option>每月</option>
                    <option>每年</option>
                </select>
            </div>
        </div>
        <button class="but">保存</button>
    </div>
</template>
<script> 
export default {
    
}
</script>
<style scoped>
@import "../assets/icomoon/style.css";
.square{
    /* width:100vmin;
    height:15vmax; */
    width:100vw;
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
.inputBox{
    width: 100%;
    height: 50vh;
    /* background-color: brown; */
    display: flex;
    flex-direction: column;
    align-items:center;
    margin-top: 1vh;
}
.eventName,.date,.kind,.overHead,.repitition{
    width:100vw;
    height: 6vh;
    /* background-color: white; */
    /* border-radius:4vw; */
    display: flex;
    margin-top: 1vh;
}
.but{
    width:30vw;
    height: 6vh;
    background-color:  rgb(53, 162, 189);
    border-color: rgb(53, 162, 189);
    margin-top: 2vh;
    border-radius:4vw;

}
.eventName span,.date span,.kind span,.overHead span,.repitition span {
    width:11vw;
    height: 6vh;
    font-size:3.5vh;
    display: flex;
    justify-content:center;
    align-items:center;
    color: rgb(53, 162, 189);
}

.eventName input,.date input{
    width:89vw;
    height: 6vh;
    font-size:2vh;
    outline: none;
    background-color: rgb(131, 222, 225);
    border-width:0px 0px 1px 0px;
    border-color:  rgb(53, 162, 189);
    border-style:solid;
    color: rgb(97, 111, 111);
}
.kind>div,.overHead>div,.repitition>div{
    width:89vw;
    height: 6vh;
    font-size:2vh;
    background-color: rgb(131, 222, 225);
    border-width:0px 0px 1px 0px;
    border-color:  rgb(53, 162, 189);
    border-style:solid;
    display: flex;
    align-items: center;
    color:rgb(97, 111, 111);
    /* flex跟末端对齐 */
    justify-content: space-between;
}
.kind div select{
    width:15vw;
    height: 6vh;
    outline: none;
    background-color: rgb(131, 222, 225);
    border: none;
}
.repitition div select{
    width:15vw;
    height: 6vh;
    outline: none;
    background-color: rgb(131, 222, 225);
    border: none;
}
.switch{
    width:4vh;
    height:4vh;
    background-color: brown;
    display:flex;
    /* justify-content: center; */
    align-items:center;
}
.down{
    width:3vh;
    height:1.5vh;
    background-color: white;
    border-radius:0.4vh;
}
.circle{
    width:3vh;
    height:3vh;
    background-color: blue;
    border-radius:50%;
    margin-left: 1.5vh;
}
</style>