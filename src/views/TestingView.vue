<script setup>
    import { ref } from 'vue'

    const count = ref(0)
    const refCount = ref(5)
    const otherCount = ref(10)
    function refIncrement(num) {
        count.value++
        refCount.value+=num
        otherCount.value+=num
    }


</script>

<template>
    <div class="container">
        <header class="header">
            <h1>TESTING VIEW</h1>
        </header>
        <div class="row">
            <p>Count is: + {{ count + 18 }}</p>
            <p>{{ refCount }}</p>
            <p>{{ otherCount }}</p>
            <button class="btn" v-on:click="refIncrement(+5)">Count</button>
        </div>   
    </div>
</template>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
        flex: 0 0 100%;
        max-width: 100%;
    }

    header h1 {
        display: flex;
        justify-content: center;
        color: cadetblue;
    }

    .row {
        display: flex;
        flex-direction: column;
        flex: 0 0 100%;
        max-width: 100%;
        flex-wrap: wrap;
    }

    .btn {
        border: none;
        outline: none;
        width: 150px;
        height: 40px;
        text-align: center;
        border-radius: 22px 8px;
        background-color: var(--vt-c-black-mute);
        box-shadow: 2px 2px 1px 1px var(--vt-c-black), -2px -2px 1px 1px var(--vt-c-black);
    }
    .btn:active {
        transform: scale(0.95);
    }
</style>