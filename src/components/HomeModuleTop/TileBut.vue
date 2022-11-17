<template>
    <div class="tileBut" @click="TileBut">
        <div>
            <div></div>
            <div></div>
        </div>
        <div> 
            <div></div>
            <div></div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{

        }
    },
    methods:{
        TileBut(){
            this.$emit('TileBut')
        }
    }
}
</script>
<style scoped>
.tileBut{
    width: 4vh;
    height:4vh;
    /* background-color: brown; */
    margin-top:4vh;
    flex-grow: 1;
    box-sizing: border-box;
    /* padding-left: 4vh; */
    display:flex;
    flex-wrap:wrap;
    /* 水平，垂直居中 */
    justify-content: center;
    /* align-items: center; */
    /* justify-content: space-between; */

}
.tileBut div{
    display: flex;
    flex-direction: column;
    justify-content:space-between;
    margin-left:0.3vh;
}
.tileBut div div{
    width:1.7vh;
    height:1.7vh;
    background-color: white;
}
</style>