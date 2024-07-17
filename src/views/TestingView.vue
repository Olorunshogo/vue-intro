<script setup>
    import { ref, reactive, computed } from 'vue'

    const count = ref(0)
    const refCount = ref(5)
    const otherCount = ref(10)
    function refIncrement(num) {
        count.value++
        refCount.value+=num
        otherCount.value+=num
    }
    const author = reactive({
        name: 'John Doe',
        books: [
            // 'Vue 2 - Advanced Guide',
            // 'Vue 3 - Basic Guide',
            // 'Vue 4 - The Mystery'
        ]
    })

    // A computed ref
    const publishedBooksMessage = computed(() => {
        return author.books.length > 0 ? 'Yes, ' + 'the author has published ' + author.books.length + ' books.' :
         'No. The author has published ' + author.books.length + ' books.'
    })

    // Class and Style Binding
    const styleObject = reactive({
        color: 'red',
        fontSize: '30px'
    })


</script>

<template>
    <div class="container">
        <header class="header" title="Header">
            <h1>TESTING VIEW</h1>
        </header>
        <div class="row" title="Reactivity Fundamentals">
            <p>Count is: + {{ count + 18 }}</p>
            <p>{{ refCount }}</p>
            <p>{{ otherCount }}</p>
            <button class="btn" v-on:click="refIncrement(+5)">Count</button>
        </div>
        <div class="row" title="Computed Properties">
            <p>Has this author published any book?</p>
            <p><span>{{ publishedBooksMessage}}</span></p>
        </div>  
        <div class="row">
            <div v-bind:style="styleObject"></div>
            <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
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