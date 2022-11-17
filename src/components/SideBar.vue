<template>
    <div class="bigBox" @touchstart="TouchStart" @touchend="TouchEnd" @touchmove="onTouchMove">
        <div class="square">
         <span>倒数日分类</span>
        </div>
        <div class="content"> 
            <div>全部
                <div>3</div>
            </div>
            <div>生活
                <div>1</div>
            </div>
            <div>工作
                <div>1</div>
            </div>
            <div>纪念日
                <div>1</div>
            </div>
            <div v-for="item5 in BookKind2" :key="item5">{{item5.name}}</div>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        BookKind2:Array,
        close: Function,
    },
    data(){
        return{
            startT1:'',
            startX:'',
            startY:'',
            endT2:'',
            endX:'',
            endY:'',
            time:'',
            Touch:'',
        }
    },
    methods:{

        onTouchMove(e){
            const a =(new Date()).valueOf()
            console.log('Touchmove触发时间:'+ a)
            console.log(e);
            this.endX=e.touches[0].clientX
            this.endY=e.touches[0].clientY
            console.log('endX:'+this.endX+',endY:'+this.endY)
        },
        TouchStart(e){
            console.log('TouchStart触发了');
            console.log(e);
            this.startT1=(new Date()).valueOf()
            console.log('TouchStart触发时间'+this.startT1)
            console.log('startX:'+this.startX)
            console.log(this.BookKind2)
            this.startX=e.touches[0].clientX
            this.startY=e.touches[0].clientY
            console.log('startX:'+this.startX+',startY:'+this.startY)
        },
        TouchEnd(e){
            console.log('TouchEnd触发了');
            console.log(e);
            this.endT2=(new Date()).valueOf()
            console.log('TouchStart触发时间'+ this.endT2)
            this.time=this.endT2-this.startT1;
            console.log('总时间time：'+this.time)
            console.log(this.BookKind2)
            //判断滑动向左的方向
            if((this.endX<this.startX)&&(this.startX-this.endX>50)&&((this.endY-this.startY===0&&this.endX<this.startX)||((this.startX-this.endX)>(this.startY-this.endY))||((this.startX-this.endX)>(this.endY-this.startY)))){
                console.log('向左滑动了')
                this.close()
            }
        }
    }
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
.square span{
    margin-top: 4vh;
    font-size: 3vh;
    color:white;
    margin-left:6vw;
}
.content>div{
    width: 65vw;
    /* height:10vh; */
    margin-top: 3vh;
    margin-bottom: 3vh;
    margin-left: 4vw;
    font-weight: 100;
    color:rgb(172, 179, 186);
    display:flex;
    font-size:3vh;
    justify-content:space-between
}
.content>div>div{
    width: 10vw;
    background-color: rgb(172, 179, 186);
    color: black;
    border-radius: 2vw;
    display: flex;
    justify-content: center;
}
</style>