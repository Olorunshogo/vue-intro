<script setup>
    import { ref, reactive, computed } from 'vue'

    // Reactivity Fundamentals
    const count = ref(0)
    const refCount = ref(5)
    const otherCount = ref(10)
    function refIncrement(num) {
        count.value++
        refCount.value+=num
        otherCount.value+=num
    }
    // Computed Properties
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

    // List Rendering
    const parentMessage = ref('Full Name: ')
    const items = ref([
        { message: 'John Babtunde Doe'}, 
        { message: 'Doe Babatunde John' }
    ])
    const myObject = reactive({
        title: 'How to do lists in Vue',
        author: 'John Doe',
        publishedAt: '20-07-2024'
    })

    // Mutation Methods
    const mutationMethods = ref([
        { method: 'push()' },
        { method: 'pop()' },
        { method: 'shift()' },
        { method: 'unshift()' },
        { method: 'splice()' },
        { method: 'sort()' },
        { method: 'reverse()' }
    ])
    // Non Mutation Methods
    const nonMutationMethods = ref([
        { method: 'filter()' },
        { method: 'concat()' },
        { method: 'slice()' }
    ])
    // Replacing an Array
    const numbers = ref([1, 2, 3, 4, 5])
    const evenNumbers = computed(() => {
        return numbers.value.filter((n) => n % 2 === 0)
    })
    const sets = ref([
        [1, 2, 3, 4, 5],
        [6, 7, 8, 9, 10]
    ])
    function even(numbers) {
        return numbers.filter((number) => number % 2 === 0 )
    }


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
        <div class="row" title="Conditional Rendering">
            <!-- <button class="btn" @click="awesome">Toggle V-If</button>
            <h2 v-if="awesome">Vue is awesome!</h2>
            <h2 v-else>Oh no &#128546;</h2> -->

            <!-- <h2 v-show="ok">Hello!</h2> -->
        </div>
        <div class="row" title="List Rendering">
            <h3>List 1</h3>
            <li v-for="(item, index) in items">
                {{ parentMessage }} {{ item.message }} - {{ index }} 
            </li>
            <h3>List 2</h3>
            <li v-for="{ message } in items">
                {{ message }}
            </li>
            <h3>List 2 with Index Alias</h3>
            <li v-for="({ message }, index) in items">
                {{ message }} {{ index }}
            </li>
            <h2>v-for with an Object</h2>
            <ul>
                <span v-for="(value, key, index) in myObject">
                    {{ index + 1 }}. {{ key }}: {{ value }}
                </span>
            </ul>
            <h3>Mutation Methods</h3>
            <ul>
                <li v-for="({ method }, index) in mutationMethods">
                    {{ method }}
                </li>
            </ul>
            <h3>Non Mutation Methods</h3>
            <ul>
                <li v-for="({ method }, index) in nonMutationMethods">
                    {{ method }}
                </li>
            </ul>
            <ul v-for="numbers in sets">
                <li v-for="n in even(numbers)">
                    {{ n }}
                </li>
            </ul>
            <h3>Even Number</h3>
            <ul>
                <li v-for="n in evenNumbers">
                    {{ n }}
                </li>
            </ul>
            
            
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