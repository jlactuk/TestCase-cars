<script setup>
    const props = defineProps(['infoCar'])
    
</script>
<template>
    <section>
        <article class="carInfo">
            <img :src="props.infoCar.preview || props.infoCar.placeholder">
            <p class="title">{{props.infoCar?.vehicle_name ? props.infoCar.vehicle_name : "No name" }}</p>
            <p class="carNumber">WDB {{props.infoCar.vin}}</p>
        </article>
        <hr>
        <article class="salesInfo">
            <p class="salesCount success">30/30</p>
            <p>3 days left</p>
        </article>
        <button class="menu">...</button>
    </section>
</template>
<style scoped>
section {
    max-width: 350px;
    background-color: #F3F6F8;
    border-radius: 10px;
    position: relative;
    padding: 35px 35px 10px;
    box-sizing: border-box;
}
p {
    text-align: left;
}
hr {
    border: none;
    height: 1px;
    background-color: #E4E4E4;
    margin: 1em 0;
}
.title {
    margin-top: 1em;
    margin-bottom: .5em;
    font-weight: 700;
    font-size: 1.25em;
}
.carNumber {
    color: #29314899;
}
.salesInfo {
    display: flex;
    justify-content: space-between;
}
.salesCount {
    display: flex;
    align-items: center;
    border-radius: 8px;
    background-color: #EDEDED;
    padding: 4px 14px;
}
.salesCount.success {
    background-color: #E4F5DD;
}
.salesCount.success::before {
    content: '';
    display: block;
    background-image: url('../assets/checkMark.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    margin-right: 5px;
    width: 16px;
    height: 16px;
}
.menu {
    border: none;
    outline: none;
    font-size: 2em;
    letter-spacing: 1px;
    background: transparent;
    color: #29314899;
    position: absolute;
    top: -10px;
    right: 10px;
}
img {
    min-height: 190px;
    width: 100%;
    height: 100%;
}
</style>