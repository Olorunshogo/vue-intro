
<script setup>
    import { ref } from 'vue'

    const count = ref(0)
    function increment(num) {
        count.value+=num
    }
    function decrement(num) {
        count.value-=num
    }

    // PROPS
    defineProps(['title'])
</script>

<template>
    <div class="mainRow">
        <div class="title">
            <h3>{{ title }}</h3>
        </div>
        <p>You clicked me {{ count }} times.</p>
        <div class="buttonWrapper">            
            <button v-on:click="increment(+5)" class="btn">Count</button>
            <button v-on:click="decrement(2)" class="btn">Countdown</button>
        </div>
    </div>

    
</template>



<style scoped>
    .mainRow {
        display: flex;
        flex-direction: column;
        padding: 0.4rem 0;
        margin: 0 auto;
    }

    .mainRrow .title h3 {
        margin: 1rem auto;
    }

    .buttonWrapper {
        display: flex;
        flex-direction: row;
        flex: 0 0 100%;
        max-width: 100%;
        padding: 0.4rem 0;
    }

    .buttonWrapper h2 {
        margin: 1rem auto;
    }

    .btn {
        border: none;
        outline: none;
        width: 150px;
        height: 40px;
        margin-right: 2rem;
        text-align: center;
        border-radius: 22px 8px;
        background-color: var(--vt-c-black-mute);
        box-shadow: 2px 2px 1px 1px var(--vt-c-black), -2px -2px 1px 1px var(--vt-c-black);
    }
    .btn:active {
        transform: scale(0.95);
    }
</style>