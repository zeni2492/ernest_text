<template>
    <header class="title">Invictus</header>
    <main class="main-container">
        <span class="buttons-container">
            <button class="quatrain-controller first-quatrain-button"></button>
            <button class="quatrain-controller second-quatrain-button"></button>
            <button class="quatrain-controller third-quatrain-button"></button>
            <button class="quatrain-controller fourth-quatrain-button"></button>
        </span>
        <div class="quatrain ">
            <first_quatrain />
        </div >
        <div class="quatrain ">
            <second_quatrain />
        </div >
        <div class="quatrain ">
            <third_quatrain />
        </div>
        <div class="quatrain ">
            <fourth_quatrain />
        </div>
    </main>
</template>

<script>
import first_quatrain from './quatrains/first_quatrain.vue';
import second_quatrain from './quatrains/second_quatrain.vue';
import third_quatrain from './quatrains/third_quatrain.vue';
import fourth_quatrain from './quatrains/fourth_quatrain.vue';
export default {
    components: {
        first_quatrain,
        second_quatrain,
        third_quatrain,
        fourth_quatrain
    }
}
</script>

<style>
.title {
    color: black;
    font-weight: 500;
    font-size: 50px;
    text-align: center;
}

.quatrain-controller{
    position: relative;
    background-color: black;
    border: none;
    width: 20px;
    height: 20px;
    margin-left: 15px;
    cursor: pointer;
}

.main-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-top: 10px;
    width: 300px;
    text-align: center;
}

h2 {
    color: black;
    font-weight: 500;
    font-size: 30px;
}
</style>