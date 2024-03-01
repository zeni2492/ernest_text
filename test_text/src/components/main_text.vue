<template>
    <header>
        <div class="title">
            <h1 class="title__name">Invictus</h1>
        </div>
        <div class="author">
            <h2 class="author__name">By William Ernest Henley</h2>
        </div>
    </header>

    <main class="main_text">
        <nav class="buttons">
            <button @click="toggleActive(1); toggleComponent(1)" :class="[{'active': isActive[1]},'button_controller']"></button>
            <button @click="toggleActive(2); toggleComponent(2)" :class="[{'active': isActive[2]},'button_controller']"></button>
            <button @click="toggleActive(3); toggleComponent(3)" :class="[{'active': isActive[3]},'button_controller']"></button>
            <button @click="toggleActive(4); toggleComponent(4)" :class="[{'active': isActive[4]},'button_controller']"></button>
        </nav>
        <div class="quatrain_container">
            <div v-if="showComponent[1]" class="first_quatrain">
                <first_quatrain/>
            </div>
            <div v-if="showComponent[2]" class="second_quatrain">
                <second_quatrain/>
            </div>
            <div v-if="showComponent[3]" class="third_quatrain">
                <third_quatrain/>
            </div>
            <div v-if="showComponent[4]" class="fourth_quatrain">
                <fourth_quatrain/>
            </div>
        </div>
    </main>
</template>

<script>
import first_quatrain from './quatrains/first_quatrain.vue';
import second_quatrain from './quatrains/second_quatrain.vue';
import third_quatrain from './quatrains/third_quatrain.vue';
import fourth_quatrain from './quatrains/fourth_quatrain.vue';
export default {
    data() {
        return {
            isActive: {
                1: false,
                2: false,
                3: false,
                4: false
            },
            showComponent:{
                1: true,
                2: true,
                3: true,
                4: true
            }
        }
    },
    components: {
        first_quatrain,
        second_quatrain,
        third_quatrain,
        fourth_quatrain
    },
    methods: {
        DontHideElementWhenItLast(){
            return Object.values(this.isActive).filter(Boolean).length;
        },
        toggleComponent(ComponentNumber) {
           if(this.DontHideElementWhenItLast() < 3 || this.isActive[ComponentNumber]){
               this.showComponent[ComponentNumber] = !this.showComponent[ComponentNumber];
           }
        },
        toggleActive(buttonNumber) {
           if(this.DontHideElementWhenItLast() < 3 || this.isActive[buttonNumber]){
            this.isActive[buttonNumber] = !this.isActive[buttonNumber];
           }
        }
    }
}
</script>

<style>
header {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.title {
    margin-right: 50px;
    text-align: center;
}

.author {
    position: absolute;
    right: 30%;
    top: 50%;
    transform: translateY(-50%);
}
.author__name {
    font-size: 15px;
}

.main_text {
    width: 100%;
    display: flex;
    justify-content: center;
    position: relative;
}

.quatrain_container{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 500px;
    text-align: center;
}

.buttons{
    position: absolute;
    margin-top: 30px;
    left: 20%;
}

.button_controller{
    width: 20px;
    height: 20px;
    margin: 5px;
    border: 2px solid black;
    background: #000;
    cursor: pointer;
}

.button_controller.active{
    background: #00000015;
}

@media (min-width: 450px) and (max-width: 1000px) {
    .author{
        right: 4%;
    }
    
}

@media (min-width: 450px) and (max-width: 1200px) {
    .title{
        text-align: center;

    }
    .author{
        right: 4%;
    }
    .quatrain_container{
        margin-top: 50px;
    }

    .buttons{
        left: 50%;
        margin-top: 5px;
        transform: translateX(-50%);
    }
}

@media (max-width: 450px) {
    .title{
       text-align: center;
    }
    .author{
        top: 50px;
        right: 50%;
        transform: translateX(50%);
        text-wrap: nowrap;
    }
    .quatrain_container{
        margin-top: 50px;
    }

    .buttons{
        left: 50%;
        margin-top: 5px;
        transform: translateX(-50%);
    }
}

@media (min-width: 1400px) {
    .title{
        text-align: center;
    }
    .title__name{
        font-size: 60px;
    }
    .author__name{
        font-size: 35px;
    }
    .author{
        right: 5%;
    }
    h2{
        font-size: 40px;
    }
    .button_controller{
        width: 40px;
        height: 40px;
    }
    .buttons{
        left: 15%;
    }
    
}

@media (min-width: 2200px) {
    .author{
        right: 25%;
    }

    .buttons{
        left: 25%;
    }
}

@media (min-width: 4000px) {
    .author{
        right: 35%;
    }
    .buttons{
        left: 35%;
    }
}
</style>
