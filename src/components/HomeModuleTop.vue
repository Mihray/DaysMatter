<template>
    <div class="square">
            <LeftMenu></LeftMenu>
            <span class="span-title">倒数日</span>
            <TileBut></TileBut>
            <AddBut @addDayBtn="addDayBtn"></AddBut>
    </div>
</template>
<script>
import LeftMenu from './HomeModuleTop/LeftMenu.vue'
import TileBut from './HomeModuleTop/TileBut.vue'
import AddBut from './HomeModuleTop/AddBut.vue'

export default{
    components:{
        LeftMenu,
        TileBut,
        AddBut
    },
    data(){
        return{

        }
    },
    methods:{
        addDayBtn(){
            console.log('传到TopModule了')
            this.$emit('addDayBtn')
        }
    }
}
</script>
<style scoped>
.square{
    /* width:100vmin;
    height:15vmax; */
    width:100vw;
    height:10vh;
    background-color: rgb(53, 162, 189);
    position: absolute;
    display: flex;
}
.Hometop{
    width:100vw;
    height:10vh;
    background-color: rgb(53, 162, 189);
    position: absolute;
    display: flex;
}
.span-title{
    font-size:3vh;
    margin-top:4vh;
    /* margin-left: 1.5vh; */
    color: white;
    flex-grow: 3;
}
/* @media screen  and (min-width: 350px){
    .span-title{
        margin-left: 1.5vh;
    }
    .square{
        background-color: rgb(189, 53, 76);
    }
} */
/* @media screen  and(max-height:670px){
    .span-title{
        font-size:18px;
        background-color: black;
    }
} */
</style>