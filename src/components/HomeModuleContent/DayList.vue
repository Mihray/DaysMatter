<template>
    <div class="dayList" @touchstart="touchstartList" @touchend="touchendList" @touchmove="touchmoveList">
        <ul :class="{dayListNew:!(TileButVar)}">
            <li v-for="item in eventList" :key="item" @click="ShowInfo($emit('ShowInfo',item))" 
            @touchstart="touchstartDel" @touchend="touchendDel" 
            :class="{overHead:item.overHeadVar}">{{item.name}}
                <ul class="deletaBox" v-if="delShow">
                        <li @click="delList">删除</li>
                        <li>置顶</li>
                </ul>
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
            touchEmit:Boolean,
         } ,
         data(){
            return{
                //判断list thouch 事件用
            listStartT1:'',
            listStartX:undefined,
            listStartY:undefined,
            listEndT2:'',
            listEndX:undefined,
            listEndY:undefined,
            listETime:'',
            listTouch:'',
            distance:'',
            //长按（删除）事件用
            DelStartT1:'',
            DelEndT2:'',
            DelTime:'',
            delShow:[],
            }
         },
         methods:{
            //实现滑动操作
            //方向判断
            touchstartList(el){
                if(this.touchEmit===true){
                    this.listStartT1=(new Date()).valueOf()
                    this.listStartX=el.touches[0].clientX
                    this.listStartY=el.touches[0].clientY
                    console.log('listStartX:'+this.listStartX+',listStartY:'+this.listStartY)
                }
            },
            touchmoveList(el){
                if(this.touchEmit===true){
                    this.listEndX=el.touches[0].clientX
                    this.listEndY=el.touches[0].clientY
                    console.log('listEndX:'+this.listEndX+',listEndY:'+this.listEndY)
                }
            },
            touchendList(){
                if(this.touchEmit===true){
                    this.listEndT2=(new Date()).valueOf()
                    this.listETime=this.listEndT2-this.listStartT1
                    console.log('listETime:'+this.listETime)
                    //向上判断
                    this.distance=Math.abs(this.listEndY-this.listStartY)
                    if((this.listStartY>this.listEndY)&&(this.listStartY-this.listEndY>20)&&((this.listStartX-this.listEndX===0)||((this.listStartY-this.listEndY)>(this.listStartX-this.listEndX))||((this.listStartY-this.listEndY)>(this.listEndX-this.listStartX)))){
                        console.log('向上滑动了'+this.distance+'px')
                    }
                    //向下判断
                    if((this.listStartY<this.listEndY)&&(this.listEndY-this.listStartY>20)&&((this.listStartX-this.listEndX===0)||(Math.abs((this.listStartY-this.listEndY))>Math.abs((this.listStartX-this.listEndX))))){
                        console.log('向下滑动了'+this.distance+'px')
                    }
                    this.listEndX=undefined
                    this.listEndY=undefined
            }
         },
         //长按弹窗
         touchstartDel(){
            this.DelStartT1=(new Date()).valueOf()
         },
         touchendDel(){
            this.DelEndT2=(new Date()).valueOf()
            this.DelTime=this.DelEndT2-this.DelStartT1
            if(this.DelTime>200){
                console.log('长按时间是：'+this.DelTime)
                this.delShow=true
            }
         },
         delList(){
            this.$emit('delList')
         }
}
}
</script>
<style scoped>
.dayList{
    margin-top: 1vh;
    /* overflow:hidden; */
    overflow: scroll;
}
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
.dayList ul .overHead{
    width:85vw;
    height: 6vh;
    background-color: rgb(220, 234, 233);
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
.dayList ul .overHead div{
    width:30vw;
    height: 6vh;
    background-color:rgb(91, 146, 159);
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
    flex-wrap: wrap;
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
    margin-top: 3vh;
}
.dayList .dayListNew li div{
    width:20vw;
    height:10vh;
    background-color: rgb(53, 162, 189);
    box-sizing: border-box;
}
.deletaBox{
    width:10vw;
    height:7vh;
    list-style: none;
    /* font-size: 1vh; */
    padding: 0;
}
.dayList ul li .deletaBox li{
    width:10vw;
    height:3.5vh;
    background-color: bisque;
    border-radius:0;
    font-size: 2.2vh;
    font-weight: 200;
    padding-left: 0;
    margin-top: 0;
    display: flex;
    /* 让元素贴右边对齐 */
    justify-content:center;
    /* align-items:center; */
    margin-top: -1.5vh;
    padding-top: 0.6vh;
}
</style>