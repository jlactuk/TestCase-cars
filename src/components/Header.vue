<script setup>
import {inject} from 'vue';
const countVechicles = inject("countVechicles");
</script>

<template>
    <header>
        <article class="titleHeader">
            <h2 class="title">Vechicles</h2>
            <button>{{ countVechicles }}</button>
        </article>
        <section class="settings">
            <button class="plusButton">+</button>
            <article class="profile">
                <img src="../assets/photo_profile.png" alt="Image" class="profileImage">
                <p class="profileName">John Doe</p>
            </article>
            <article class="chooseLanguage">
                <img src="../assets/uk.png" alt="English">
                <p>En</p>
            </article>
        </section>

    </header>
</template>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        padding: 10px 30px;
        color: #293148;
        background: #FFF;
        border-bottom: 1px solid #E4E4E4;
    }
    .titleHeader {
        display: flex;
        gap: 20px;
        align-items: center;
    }
    .title {
        font-size: 2em;
    }
    .titleHeader button {
        color: #293148CC;
        background-color: #F3F6F8;
        border: none;
        padding: 10px;
    }
    .settings {
        display: flex;
        gap: 20px;
        align-items: center;
        width: fit-content;
    }
    .plusButton {
        border: 1px solid #E86E84;
        color: #E86E84;
        padding: 9px;
        border-radius: 6px;
        cursor: pointer;
        background-color: transparent;
    }
    .profile {
        display: flex;
        align-items: center;
        gap: 10px;
    }
    .profileImage {
        width: 46px;
        height: 46px;
        border-radius: 23px;
    }
    .chooseLanguage {
        display: flex;
        align-items: center;
        gap: 10px;
        cursor: pointer;
    }
    .chooseLanguage img {
        width: 24px;
        height: 24px;
        border-radius: 12px;
    }
    .chooseLanguage p {
        font-size: 15px;
        width: fit-content;
    }
    .chooseLanguage p::after {
        content: "";
        display: inline-block;
        width: 10px;
        height: 10px;
        margin-left: 10px;
        background: url("../assets/chevron_down.png");
        background-repeat: no-repeat;
        background-position: center;
        background-size: contain;
        transition: .3s;
    }
    .chooseLanguage p:hover::after {
         transform: rotateX(180deg);
    }
</style>