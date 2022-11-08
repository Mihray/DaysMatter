<template>
    <div class="square">
        <div class="menu-line">
            <div></div>
            <div></div>
            <div></div>
        </div>
    </div>
</template>
<script>

</script>
<style scoped>
.square{
    /* width:100vmin;
    height:15vmax; */
    width:100vw;
    height:10vh;
    background-color: rgb(53, 162, 189);
    position: absolute;
}
.menu-line{
    width: 4vh;
    height:4vh ;
    /* background-color: brown; */
    margin-top:4vh;
    margin-left: 3vh;
    /* box-sizing: border-box; */
    display: flex;
    flex-direction: column;
    /* align-content:space-between; */
    justify-content:space-between;
}
.menu-line div{
    /* box-sizing: inherit; */
    width: 4vh;
    height:0.9vh ;
    background-color: white;
    /* align-content:space-between; */
}
/* .menu-line div:first-child{
    align-items:flex-start;
}
.menu-line div:last-child{
    align-items:flex-end;
} */
</style>