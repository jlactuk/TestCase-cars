<script setup>
    import {ref,watch, onMounted, watchEffect, inject} from "vue"
    import Controls from "./Controls.vue"
    import Card from "./carCard.vue"
    import Paggination from "./Paggination.vue"
        const cars = ref([])
        const metaData = ref('');
        const apiData = ref({
            currentPage: 1,
            perPage: 9,
            search: ''
        })
        const countVechicles = inject("countVechicles");
        watchEffect(async () => {
            fetch(`https://api.caiman-app.de/api/cars-test?per_page=${apiData.value.perPage}&page=${apiData.value.currentPage}&search=${apiData.value.search}`)
             .then(response => response.json())
             .then(data => {
                cars.value = data.data
                metaData.value = data.meta;
                countVechicles.value  = data.meta.total
              })
             .catch(error => console.error('Error:', error))
        })
</script>
<template>
    <section>
        <Controls 
        v-model:="apiData"
          />

        <section class="Cards">
            <Card v-if="cars.length > 0" v-for="car in cars" :key="car.id" :infoCar='car'/>
            <p v-else class="notFound">No cars found</p>
          
        </section>
        <Paggination v-if="metaData" :pageInfo='metaData' v-model="apiData.currentPage" />
    </section>
</template>

<style scoped>
.Cards {
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 30px;
    padding: 20px 30px;
}
.notFound {
    text-align: center;
    font-size: 24px;
    width: 100%;
    grid-column: 1/4;

    margin-top: 30px;
}

@media screen and (min-width: 1441px) {
    .Cards {
    gap: 20px;
    grid-template-columns: repeat(5,1fr);

    }
    .notFound {
        grid-column: 1/6;
    }
}
</style>