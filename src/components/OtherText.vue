

<script setup>
defineOptions({
    inheritAttrs: false
})
    // import { ref } from 'vue'
    // const parentModel = ref(0)

    // const parentModel = defineModel()   
    // function update() {
    //     parentModel.value++
    // }

    const props = defineProps(['parentModel'])
    const emit = defineEmits(['update:parentModel'])
</script>

<template>
    <div class="row" title="Parent Bound V-Model">
        <h3>OtherText</h3>
        <!-- <p>Parent bound text is: {{ parentModel }}</p>
        <button class="btn" v-on:click="update">Increment</button> -->

        <input
            v-bind:value="props.parentModel"
            @input="emit('update:parentModel', $event.target.value)"
        />

        <!-- <input type="text"
            v-bind:value="props.modelValue"
            @input="emit('update:modelvalue', $event.target.value)"
        /> -->
    </div>
</template>

<style scoped>
    .row {
        display: flex;
        flex-direction: column;
        flex: 0 0 100%;
        max-width: 100%;
        flex-wrap: wrap;
        padding: 1rem 0.5rem;
    }

    .row h2 {
        margin: 1rem auto;
    }

    .btn {
        border: none;
        outline: none;
        width: 150px;
        height: 40px;
        margin: 8px 0;
        text-align: center;
        border-radius: 22px 8px;
        background-color: var(--vt-c-black-mute);
        box-shadow: 2px 2px 1px 1px var(--vt-c-black), -2px -2px 1px 1px var(--vt-c-black);
    }
    .btn:active {
        transform: scale(0.95);
    }

    input,
    input[type=text] {
        border: 1px solid #555;
        font-family: inherit;
        outline: none;
        background-color: var(--color-background);
        color: #ddd;
        padding: 1rem 0.5rem;
        height: 35px;
        width: 70%;
        margin: 8px 0;
        border-radius: 6px;
        transition: all 0.5s ease-in-out;
    }

    input[type=text]:focus {
        border: 1px solid blue;
        background-color: #111;
    }

    input[type=text]::placeholder {
        font-weight: 600;
        font-size: 0.8rem;
        padding-bottom: 50px;
    }
    
</style>