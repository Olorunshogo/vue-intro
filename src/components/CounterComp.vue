
<script setup>
    import { ref } from 'vue'

    const count = ref(0)
    function increment(num) {
        count.value+=num
    }
    function decrement(num) {
        count.value-=num
    }

</script>

<template>
    <div>
        <p>You clicked me {{ count }} times.</p>
        <button v-on:click="increment(+5)" class="btn">Count</button>
        <button v-on:click="decrement(-2)" class="btn">Countdown</button>
    </div>
</template>



<style scoped>
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