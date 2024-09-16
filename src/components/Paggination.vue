<script setup>

    const props = defineProps(['pageInfo']);
    const model = defineModel();
    function changePage(changePosition) {
       model.value += changePosition;
    }
    console.log(props.pageInfo);

</script>
<template>
    <section>
        <p>Showing {{ props.pageInfo.to || 0 }} out of {{ props.pageInfo.total }}</p>
        <article class="pages">
            <button @click="changePage(-1)" :disabled="props.pageInfo.current_page === 1"> <img src="../assets//chevron_down.png" alt="<" class="prevPage"></button>
            <p><span>{{  props.pageInfo.current_page }}</span> of <span class="maxPage">{{  props.pageInfo.last_page }}</span></p>
            <button @click="changePage(1)" :disabled="props.pageInfo.current_page === props.pageInfo.last_page"> <img src="../assets//chevron_down.png" alt=">" class="nextPage"></button>
        </article>
    </section>
</template>
<style scoped>
section,
article {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px;
}
section {
    justify-content: space-between;
}
span {
    margin: 0 5px;
    padding: 5px 10px;
    border-radius: 6px;
    border: 1px solid #E4E4E4;
}
span.maxPage {
    color: #29314873;
}
img {
    cursor: pointer;
}
.prevPage {
    transform: rotate(90deg);
}
.nextPage {
    transform: rotate(-90deg);
}
</style>