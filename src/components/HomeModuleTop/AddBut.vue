<template>
    <div class="addBut">
        <div class="addBut2"> 
            <div class="across"></div>
            <div class="vertical"></div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.addBut{
    width: 4vh;
    height:4vh ;
    /* background-color: brown; */
    margin-top:4vh;
    flex-grow: 1;
    box-sizing: border-box;
}
.addBut2{
    width: 4vh;
    height:4vh ;
    /* background-color: blue; */
    box-sizing: border-box;
    display:flex;
    align-items: center;
}
.across{
    width: 4vh;
    height: 0.6vh;
    background-color: white;
    align-items: center;
}
.vertical{
    width: 0.6vh;
    height: 4vh;
    background-color: white;
    margin-left: -2.3vh;
}
</style>