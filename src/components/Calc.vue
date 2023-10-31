<script setup>
    import { ref } from "vue";

    const varA = ref(null);
    const varB = ref(null);
    const res = ref(null);

    function tambah() {
        res.value = parseInt(varA.value) + parseInt(varB.value);
    }
    function kurang() {
        res.value = varA.value - varB.value;
    }
    function kali() {
        res.value = varA.value * varB.value;
    }
    function bagi() {
        res.value = varA.value / varB.value;
    }
</script>

<template>
    <main>
        <h1>Simple Calculator</h1>
        <div class="input-row">
            <label for="A">Number 1 : </label>
            <div>
                <input class="input-field" v-model="varA" inputmode="numeric" oninput="this.value = this.value.replace(/\D+/g, '')" id="A" required>
            </div>
            <label for="B">Number 2 : </label>
            <div>
                <input class="input-field" v-model="varB" inputmode="numeric" oninput="this.value = this.value.replace(/\D+/g, '')" id="B" required>
            </div>
        </div>
        <div class="buttons">
            <button class="button-19" @click="tambah">+</button>
            <button class="button-19" @click="kurang">-</button>
            <button class="button-19" @click="kali">&times;</button>
            <button class="button-19" @click="bagi">&div;</button>
        </div>
        <div class="result">
            <h2>Hasil : </h2>
            <h2>{{ res }}</h2>
        </div>
    </main>
</template>


<style scoped>
    main {
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .input-row{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 16px;  
    }
    .buttons{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 16px;
    }
    .result{
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .input-field {

        border: 3px solid #000;
        border-radius: 5px;
        height: 50px;
        line-height: normal;
        color: #282828;
        display: block;
        width: 100%;
        box-sizing: border-box;
        user-select: auto;
        font-size: 16px;
        padding: 0 6px;
        padding-left: 12px;
        
    
    }
    .input-field:focus{

        border: 3px solid #5551ff;
        
    }
    .button-19 {
    appearance: button;
    background-color: #1899D6;
    border: solid transparent;
    border-radius: 16px;
    border-width: 0 0 4px;
    box-sizing: border-box;
    color: #FFFFFF;
    cursor: pointer;
    display: inline-block;
    font-family: din-round,sans-serif;
    font-size: 15px;
    font-weight: 700;
    letter-spacing: .8px;
    line-height: 20px;
    margin: 0;
    outline: none;
    overflow: visible;
    padding: 13px 16px;
    text-align: center;
    text-transform: uppercase;
    touch-action: manipulation;
    transform: translateZ(0);
    transition: filter .2s;
    user-select: none;
    -webkit-user-select: none;
    vertical-align: middle;
    white-space: nowrap;
    width: 100%;
    }

    .button-19:after {
    background-clip: padding-box;
    background-color: #1CB0F6;
    border: solid transparent;
    border-radius: 16px;
    border-width: 0 0 4px;
    bottom: -4px;
    content: "";
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
    z-index: -1;
    }

    .button-19:main,
    .button-19:focus {
    user-select: auto;
    }

    .button-19:hover:not(:disabled) {
    filter: brightness(1.1);
    -webkit-filter: brightness(1.1);
    }

    .button-19:disabled {
    cursor: auto;
    }

    .button-19:active {
    border-width: 4px 0 0;
    background: none;
    }
</style>

