<template>
  <div id="app">
    <h1>Problema de Mounty Hall</h1>
        <div class="form">
            <div v-if="!started">
                <label for="portsAmount">Quantas portas?</label>
                <input type="text" id="portsAmount" size="3"
                    v-model.number="portsAmount">
            </div>
            <div v-if="!started">
                <label for="selectedPort">Qual a porta é premiada?</label>
                <input type="text" id="selectedPort" size="3"
                    v-model.number="selectedPort">
            </div>
    
            <button v-if="!started" @click="started = true">Iniciar</button>
            <button v-if="started" @click="started = false">Reiniciar</button>
        </div>
    
        <transition enter-active-class="animated pulse" leave-active-class="fadeOut" mode="out-in">
            <div class="doors" v-if="started">
                <div v-for="i in portsAmount" :key="i">
                    <Door :hasGift="i === selectedPort" :number="i"/>
                </div>
            </div>
        </transition>
  </div>
</template>

<script>
import Door from './components/DoorVue.vue'

export default {
    name: 'App',
    components: { Door },
    data(){
        return {
            started: false,
            portsAmount: 3,
            selectedPort: null
        }
    }
}
</script>

<style>

* {
    box-sizing: border-box;
    font-family: 'Mountserrat' sans-serif;

}

body {
    color: #3e7ae7;
    -webkit-text-stroke: 0.25px rgba(82, 135, 214, 0.267);
    background: linear-gradient(to right, #acb6e5, #86fde8);
}

#app {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#app h1 {
    border: 1px solid rgb(231, 224, 215);
    background-color: rgba(253, 197, 246, 0.493);
    padding: 20px;
    margin-bottom: 60px;
}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: 40px;    
}

.form, .form input, .form button {
    margin-bottom: 10px;
    font-size: 2rem;
}

.doors{
    align-self: stretch;
    display: flex;
    justify-content: space-around;

    flex-wrap: wrap;
    animation-duration: 0.3s;
}

.form input {
    background: none;
    margin-left: 5px;
    border-radius: 5px;
    width: 40px;
    outline: none;
}

.form button {
    background: none;
    border-radius: 5px;
}

.form button:hover{
    background-color: #acb6e5;
    transition: background-color 0.3s ease
}

</style>

