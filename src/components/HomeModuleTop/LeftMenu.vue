<template>
        <div class="menu-line" @click="menulineClick($emit('menulineClick'))">
            <div></div>
            <div></div>
            <div></div>
        </div>
</template>
<script>

</script>
<style scoped>
.menu-line{
    width: 4vh;
    height:4vh ;
    /* background-color: brown; */
    margin-top:4vh;
    /* margin-left: 3vh; */
    display: flex;
    flex-direction: column;
    /* align-content:space-between; */
    /* 把剩下的空间均分 */
    justify-content:space-between;
    flex-grow: 1;
    padding-left: 3vh;
    box-sizing: border-box;
}
.menu-line div{
    /* box-sizing: inherit; */
    width: 4vh;
    height:0.9vh;
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