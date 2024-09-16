<script setup></script>

<template>
    <aside>
        <h2>Demo Test</h2>

        <article class="links">
            <nav>
                <ul>
                    <li>
                        <img src="../assets/user.png" alt="Profile">
                        <a href="#">Profile</a>
                    </li>
                    <li class="active">
                        <img src="../assets/rim.png" alt="Image">
                        <a href="#">Vechicles</a>
                    </li>
                    <li>
                        <img src="../assets/settings.png" alt="Settings">
                        <a href="#">Settings</a>
                    </li>
            </ul>
            </nav>
        </article>
    </aside>

</template>

<style scoped>
    aside {
        background: #282828;
        background-image:  url('../assets/background.png');
        background-size: contain;
        background-position: 0 100%;
        background-repeat: no-repeat;
        display: flex;
        flex-direction: column;
        gap: 60px;
    }

    
    h2 {
        color: #ffffff;
    }
    
    nav {
        display: flex;
        flex-direction: column;
        gap: 10px;

    }
    ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        display: grid;
        gap: 10px;
    }
    li {
        color: #FFFFFF73;
        display: flex;
        gap: 20px;
        align-items: center;
        padding-left: 25%;
        height: 2em;
    }
    a {
        width: 30px;
        color: inherit;
        text-align: center;
    }
    li.active {
        border-left: 1px solid #D90E32;
        color: #FFFFFF;
    }

</style>