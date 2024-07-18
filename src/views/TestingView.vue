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

    // EVENT LISTENING: Method Handlers
    const name = ref('Vue.js')
    function greet(event) {
        alert(`Hello ${name.value}!`)
        // if (event) {
        //     alert(event.target.tagName + '!!!')
        // }
        
    }
    const message = ref('Form cannot be submitted yet.')
    function warn(message, event) {
        if (event) {
            event.preventDefault();
        }
        alert(message)
    }


</script>

<template>
    <div class="container">
        <header class="header" title="Header">
            <h1>TESTING VIEW</h1>
        </header>
        <div class="row" title="Reactivity Fundamentals">
            <h2>Reactivity Fundamentals</h2>
            <p>Count is: + {{ count + 18 }}</p>
            <p>{{ refCount }}</p>
            <p>{{ otherCount }}</p>
            <button class="btn" v-on:click="refIncrement(+5)">Count</button>
        </div>
        <div class="row" title="Computed Properties">
            <h2>Computed Properties</h2>
            <p>Has this author published any book?</p>
            <p><span>{{ publishedBooksMessage}}</span></p>
        </div>  
        <div class="row" title="Conditional Rendering">
            <h2>Conditional Rendering</h2>
            <!-- <button class="btn" @click="awesome">Toggle V-If</button>
            <h2 v-if="awesome">Vue is awesome!</h2>
            <h2 v-else>Oh no &#128546;</h2> -->

            <!-- <h2 v-show="ok">Hello!</h2> -->
        </div>
        <div class="row" title="List Rendering">
            <h3>List Rendering</h3>

            <h4>List 1</h4>
            <li v-for="(item, index) in items">
                {{ parentMessage }} {{ item.message }} - {{ index }} 
            </li>

            <h4>List 2</h4>
            <li v-for="{ message } in items">
                {{ message }}
            </li>

            <h4>List 2 with Index Alias</h4>
            <li v-for="({ message }, index) in items">
                {{ message }} {{ index }}
            </li>

            <h3>V-for with an Object</h3>
            <ul>
                <span v-for="(value, key, index) in myObject">
                    {{ index + 1 }}. {{ key }}: {{ value }}
                </span>
            </ul>

            <h4>Mutation Methods</h4>
            <ul>
                <li v-for="({ method }, index) in mutationMethods">
                    {{ method }}
                </li>
            </ul>

            <h4>Non Mutation Methods</h4>
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

            <h4>Even Number</h4>
            <ul>
                <li v-for="n in evenNumbers">
                    {{ n }}
                </li>
            </ul>            
        </div>

        <div class="row" title="Event Handling">
            <h2>Event Handling</h2>

            <!-- `greet` is the Name of the method defined above -->
            <button class="btn" v-on:click="greet">Greet</button>

            <!-- Using $event special variable -->
            <button class="btn" v-on:click="warn(message, $event)">
                Submit
            </button>

            <!-- Using inline arrow function -->
            <button class="btn" @click="(event) => warn(message, event)">
                Submit
            </button>

            <h3>Event Modifiers</h3>

            <!-- The click evyent's propagation will be stopped. -->
            <a @click.stop="doThis"></a>

            <!-- The default submit evyent will no longer reload the page. -->
            <form @submit.prevent="onSubmit"></form>

            <!-- modifiers can be chained -->
            <a @click.stop.prevent="doThat"></a>

            <!-- just the modifier -->
            <form @submit.prevent></form>

            <!-- only trigger handler if evyent.target is the element itself -->
            <!-- i.e. not from a child element -->
            <div @click.self="doThat">...</div>
        </div>

        <div class="row" title="Form Input Bindings">
            <h2>Form Input Bindings</h2>
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

    .row h2 {
        margin: 1rem auto;
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