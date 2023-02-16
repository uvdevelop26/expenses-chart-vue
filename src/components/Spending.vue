<script setup>
import { defineProps } from 'vue';
import { ref } from 'vue';


const { spending } = defineProps(['spending']);
const todayDate = new Date();
let currentDay = ref(todayDate.getDay());


const showData = ($event) => {
    const sibling = $event.target.previousElementSibling;
    sibling.classList.remove('display-none');
}

const hideData = ($event) => {
    const sibling = $event.target.previousElementSibling;
    sibling.classList.add('display-none');
}




//ver la barra que corresponde al día actual resaltado de un color
//diferente
//identificar la barra que corresponde al día actual
//agregarle un color diferente





</script>
<template>
    <div class="card">
        <h1 class="card-tittle text-brown">Spending - Last 7 days</h1>
        <div class="bar-container">
            <div class="bar-chart" v-for="spend in spending" :key="spend.day">
                <div class="bar-data display-none"> ${{ spend.amount }}</div>
                <div class="bar not-today-color" @mouseover="showData($event)" @mouseleave="hideData($event)"
                    :class="[spend.id === currentDay ? 'current-day-color' : '']"
                    :style="{height: spend.amount + 10 +'px'}">
                </div>
                <span class="day text-soft-brown">{{ spend.day }}</span>
            </div>
        </div>
        <div class="card-footer">
            <div class="card-text">
                <p class="text-soft-brown text-medium">Total this month</p>
                <span class="total-spending text-brown">$478.33</span>
            </div>
            <div class="card-data">
                <span class="total-porcent text-brown">+2.4%</span>
                <p class="text-soft-brown text-medium">from last month</p>
            </div>
        </div>
</div>
</template>
<style scoped>
.card {
    margin: 0 auto;
    align-self: center;
    width: 100%;
    max-width: 400px;
    background: hsl(33, 100%, 98%);
    border-radius: 10px;
    padding: 15px;
}

.text-brown {
    color: hsl(25, 47%, 15%);
}

.text-soft-brown {
    color: hsl(28, 10%, 53%);
}

.text-medium {
    font-size: .9rem;
}

.display-none {
    display: none;
}

.card-tittle {
    font-weight: 700;
    font-size: 1.4rem;
    padding-top: 8px;
}

.bar-container {
    padding-top: 10px;
    padding-bottom: 17px;
    border-bottom: 2px solid hsl(27, 66%, 92%);
    display: flex;
    justify-content: space-between;
}

.bar-chart {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: end;
    padding-top: 30px;
}

.bar-data {
    background: hsl(25, 47%, 15%);
    width: 45px;
    height: 25px;
    border-radius: 3px;
    margin-bottom: 4px;
    color: hsl(33, 100%, 98%);
    font-size: .6rem;
    font-weight: bold;
    text-align: center;
    padding-top: 5px;
    position: absolute;
    top: 0px;
}

.bar {
    width: 30px;
    border-radius: 4px;
}

.not-today-color {
    background-color: hsl(10, 79%, 65%);
}

.not-today-color:hover {
    background-color: hsl(10, 100%, 76%);
}

.current-day-color {
    background-color: hsl(186, 34%, 60%);
}

.current-day-color:hover {
    background-color: hsl(187, 49%, 81%);
}

.day {
    font-size: .8rem;
    padding-left: 2px;
    padding-top: 5px;
}

.card-footer {
    padding-top: 25px;
    display: flex;
    justify-content: space-between;
}

.card-text p {
    line-height: 15px;
}

.total-spending {
    font-size: 1.5rem;
    font-weight: 700;
}

.card-data {
    text-align: right;
    margin-top: auto;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
}

.card-data .total-porcent {
    font-size: .8rem;
    font-weight: 700;
    margin-left: auto;
    line-height: 8px;
}

.card-data p {
    line-height: 25px;
    padding-top: 0;
}
</style>