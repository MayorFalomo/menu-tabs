<template>
    <div class="cardContainer" >
        <div class="imgCon " >
        <img class="menuImg" :src="menuItem.img" alt="img" />
        </div>
        <div class="menuInfo " >
            <div class="flexInfo" >
            <h1> {{menuItem.foodName}} </h1>
            <span> {{menuItem.price}} </span>
            </div>
            <p> {{menuItem.description}} </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Menu',
    props: {
        menuItem: Object,
    },
    data() {
        return {

        }
    }
}
</script>

<style>

.imgCon{
 width: 100%;
}
.imgCon img{
    width: 100% !important;
     height: auto;
     max-height: 400px;
     object-fit: cover;
}
.menuInfo .flexInfo span{
   background-color: #F59E0B;
   padding: 5px 10px;
   color: #fff;
   font-size: 20px;
   border-radius: 6px;
}
.menuInfo p{
    font-size: 20px;
    line-height: 30px;
    padding-bottom: 10px;
    width: 90%;
    margin: 0 auto;
}
.flexInfo{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 30px auto;
    width: 90%;
}
</style>