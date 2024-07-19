<script>
    import { ref } from 'vue'

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


    // EVENT LISTENING: Method Handlers
    const name = ref('Vue.js')
    function greet(event) {
        alert(`Hello ${name.value}!`)
        if (event) {
            alert(event.target.tagName + '!!!')
        }        
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

        <div class="row" title="List Rendering">
            <h3>List Rendering</h3>

            <h4>Mutation Methods</h4>
            <ul>
                <li v-for="({ method }, index) in mutationMethods" v-bind:key="method">
                    {{ index }}. {{ method }}
                </li>
            </ul>

            <h4>Non Mutation Methods</h4>
            <ul>
                <li v-for="({ method }, index) in nonMutationMethods" v-bind:key="method">
                    {{ index }}. {{ method }}
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

            <p>Message is: {{ textMsg }}</p>
            <input type="text" v-model="textMsg" placeholder="edit me" />

            <p>Multiline msg is:</p>
            <p>{{ textareaMsg }}</p>
            <textarea v-model="textareaMsg" placeholder="add multiple lines"></textarea>


        </div>

        
    </div>
</template>

<style scoped>
    .container {
        display: grid;
        grid-template-columns: 1fr;
    }

    header h1 {
        text-align: center;
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

    input[type=text],
    textarea {
        border: 1px solid #555;
        font-family: inherit;
        outline: none;
        background-color: var(--color-background);
        color: #ddd;
        padding: 1rem 0.5rem;
        height: 35px;
        width: 200px;
        border-radius: 6px;
        transition: all 0.5s ease-in-out;
    }
    input[type=text]:focus,
    textarea:focus {
        border: 1px solid blue;
        background-color: #111;
    }
    input[type=text]::placeholder,
    textarea::placeholder {
        font-weight: 600;
        font-size: 0.8rem;
        padding-bottom: 50px;
    }
</style>