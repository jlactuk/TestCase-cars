<script setup>
const apiDataModel = defineModel();


</script>
<template>
    <section>
        <section class="controls">
            <article class="searchInput">
                <input type="text" id="VIN" placeholder="Search VIN" v-model="apiDataModel.search">
                <label for="VIN">
                    <img src="../assets/Search.png" alt="Search">
                </label>
            </article>
            <article class="chooseCountCars">
                <p>Select vehicles per page:</p>
                <select name="count" id="count" v-model="apiDataModel.perPage">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option value="7">7</option>
                    <option value="8">8</option>
                    <option value="9" selected>9</option>
                    <option value="10">10</option>
                </select>
            </article>
            <article class="addVechicle">
                <span>+</span>
                <button>add vehicles</button>
            </article>
        </section>
    </section>
</template>
<style scoped>
    .controls {
        display: flex;
        gap: 20px;
        padding: 30px 30px;
    }
    input {
        border :none;
        outline: none;    
        padding: 10px;
    }
    .searchInput {
        border: 1px solid #E4E4E4;
        border-radius: 8px;
        display: flex;
        align-items: center;
        padding: 0 5px;
    }
    .searchInput img {
        width: 80%;
        height: 80%;
    }
    .chooseCountCars {
        display: flex;
        align-items: center;
        gap: 20px;
    }
  select {
        padding: 7px 40px 7px 12px;
        width: 70px;
        border: 1px solid #E8EAED;
        border-radius: 5px;
        background: white;
        box-shadow: 0 1px 3px -2px #9098A9;
        cursor: pointer;
        font-family: inherit;
        font-size: 16px;
        transition: all 150ms ease;
    }
    select:focus {
      outline: none;
      border-color: #D90E32;
      box-shadow: 0 0 0 2px rgba(#D90E32,.2);
    }
   option {
    background-color: #fff;
   }
    button {
        cursor: pointer;
        color: inherit;
        
    }
    .addVechicle {
        display: flex;
        gap: 10px;
        color: #FFFFFF;
        background-color: #D90E32;
        border-radius: 10px;
        box-shadow: 0 8px 24px #D90E321F;
        margin-left: auto;
        align-items: center;
        justify-content: center;
        padding: 5px 25px;
        font-size: 16px;
        font-weight: bold;
        cursor: pointer;
    }
    .addVechicle:hover {
        background-color: #C40C2F;
        color: #FFFFFF;
        transition: all 150ms ease;
    }
    .addVechicle span {
        font-size: 1.2em;

    }
</style>