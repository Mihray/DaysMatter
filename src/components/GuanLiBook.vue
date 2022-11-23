<template>
    <div class="big-box">
        <div class="square">
        <div class="arrow" @click="returnHome"> 
            <div class="arrowhead"></div>
            <div class="arrowbody"></div>
        </div>
        <span>添加新本子</span>
    </div>
    <div class="BookBox">
        <ul>
            <li>
                <div class="liBox">生活</div>
            </li>
            <li>
                <div class="liBox">工作</div>
            </li>
            <li>
                <div class="liBox">纪念日</div>
            </li>
            <li v-for="item2 in kind" :key="item2">
                <div class="liBox">{{item2.name}}</div>
            </li>
            <li>
                <div class="liBox" @click="addKind">+</div>
            </li>
            <li>
                <div class="liBox" @click="deleteKind">-</div>
            </li>
        </ul>
        <div class="addKindBox" v-show="addKindShow">
            <div class="cancelBox" @click="cancelClick">
                <div class="cancelBox1"></div>
                <div class="cancelBox2"></div>
                <div class="cancelBox3"></div>
                <div class="cancelBox4"></div>
            </div>
            <input type="text" placeholder="请输入倒数本名字"   v-model="inputValue">
            <button @click="addBook">添加</button>
        </div>
    </div>
    </div>
    <!-- <bottom-vue></bottom-vue> -->
</template>
<script>

// import BottomVue from './HomeModuleContent/BottomVue.vue';

export default {
//   components: { BottomVue },
    data(){
        return{
            kind:[
                    ],
            addKindShow:false,
            // inputValue:{name:''},
            // inputArr:[]
            inputValue:''
            }
    },
    methods:{
        returnHome(){
            this.$emit('returnHome')
         },
         addKind(){
            this.addKindShow=true;
         },
         deleteKind(){

         },
         addBook(){
            this.addKindShow=false;
            // this.kind.push(this.inputValue)
            // this.inputArr.push(this.inputValue)
            // this.kind.push(this.inputArr[0])
            this.kind.push({
                name:this.inputValue
            })
            this.inputValue="";
            console.log(this.kind);
            this.$emit('UpBook',this.kind)
         },
         cancelClick(){
            this.addKindShow=false;
         }
    }
}
</script>
<style scoped>
.big-box{
    height:91vh;
    width: 100vw;
}
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
.BookBox{
    width: 100vw;
    display: flex;
    align-items: center;
}
.BookBox ul{
    width: 100vw;
    list-style: none;
    display: flex;
    box-sizing: border-box;
    padding: 0;
    flex-wrap: wrap;
}
.BookBox ul li{
    width: 30vw;
    height: 20vh;
    background-color: rgb(131, 222, 225);
    flex-grow:1;
    display: flex;
    align-items: center;
    justify-content:center;
}
.liBox{
    width: 15vw;
    height: 10vh;
    background-color:white;
    display: flex;
    align-items: center;
    justify-content:center;
}
.addKindBox{
    width:70vw;
    height: 30vh;
    background-color: rgb(53, 162, 189);
    position: absolute;
    left:50vw;
    transform:translateX(-35vw);
    border-radius: 1vh;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.cancelBox{
    width: 6vw;
    height: 6vw;
    margin-left: 65vw;
    /* background-color: rgb(53, 162, 189); */
    transform: matrix(0.71, 0.71, -0.71, 0.71, 0, 0);
    box-sizing: border-box;
    display: flex; 
    flex-wrap: wrap; 
    align-content: space-between;
    /* .column { flex-basis: 100%; display: flex; justify-content: space-between;} */
}
.cancelBox div{
    width: 3vw;
    height: 3vw;
    /* background-color: rgb(53, 162, 189); */
    box-sizing: border-box;
}
.cancelBox1{
    border-right:1vw solid white;
    border-bottom:1vw solid white;
    margin-top: 1vw;
}
.cancelBox4{
    margin-left: -1vw;
    margin-top: -1vw;
    border-left:1vw solid white;
    border-top:1vw solid white;
}
/* .cancelBox3{
    border-right:1.3vw solid white;
    border-bottom:1.3vw solid white;
} */
.addKindBox input{
    width:60vw;
    height: 6vh;
    margin-top: 5vh;
    outline: none;
    border-radius: 1vh;
}
.addKindBox button{
    width:17vw;
    height: 6vh;
    margin-top: 5vh;
    border-radius: 1vh;
}
</style>