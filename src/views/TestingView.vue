<script setup>
    // import { ref, onMounted } from 'vue'

    // EVENT LISTENING: Method Handlers
    // const vueName = ref('Vue.js')
    // function greet(event) {
    //     alert(`Hello ${vueName.value}!`)
    //     if (event) {
    //         alert(event.target.tagName + '!!!')
    //     }        
    // }

    // const msg = ref('Form cannot be submitted yet.')
    // function warn(msg, event) {
    //     if (event) {
    //         event.preventDefault();
    //     }
    //     alert(msg)
    // }

    // FORM INPUT BINDINGS
    // const textMsg = ref("") 
    // onMounted(() => {
    //    textMsg.value.focus()
    // })
    // const lazyTextMsg = ref("") 
    
    // const age = ref()

    // const textareaMsg = ref('')

    // const checked = ref('False')
    // const toggleYesNo = ref('No')
    // const toggleDynamicTrueFalse = ref("")
    // const checkedNames = ref([])

    // const picked = ref([])

    // const selected = ref("")
    // const selectedMultiple = ref([])
    // const selectedTable = ref("A")
    // const options = ref([
    //     { text: 'One', value: 'A' },
    //     { text: 'Two', value: 'B' },
    //     { text: 'Three', value: 'C' }
    // ])
    // const selectedNumber = ref()
</script>

<template>
    <div class="container">
        <header class="header" title="Header">
            <h1>TESTING VIEW</h1>
        </header>

        <div class="row" title="Event Handling">
            <!-- <h2>Event Handling</h2> -->

            <!-- `greet` is the Name of the method defined above -->
            <!-- <button class="btn" v-on:click="greet">Greet</button> -->

            <!-- Using $event special variable -->
            <!-- <button class="btn" v-on:click="warn(msg, $event)">
                $event special variable Submit
            </button> -->
        </div>
        

        <div class="row" title="Form Input Bindings">
            <!-- <h2>Form Input Bindings</h2> -->

            <div title="Text Input Fields">
                <!-- <div><h3>Text</h3>
                    <p>Message is: {{ textMsg }}</p>
                    <input type="text" v-model="textMsg"
                        name="inputText" placeholder="Input text here..."
                        ref="textMsg"
                    />
                </div> -->
                <div>
                    <!-- <h3>Text</h3> -->
                    <!-- Sync after change instead of input -->
                    <!-- <p>The lazy text message is: {{ lazyTextMsg }}</p>
                    <input type="text" v-model.lazy="lazyTextMsg" name="inputText" placeholder="Input text here..." /> -->
                </div>
            </div>

            <!-- <div title="Number">
                <p>Age is: {{ age }}</p>
                <input type="number" id="age" v-model.number="age" placeholer="Input your age here..." />
            </div>

            <div title="Textarea input Fields">
                <h3>Textarea</h3>
                <p>Message is: <span style="white-space: pre-line;">{{ textareaMsg }}</span></p>
                <textarea v-model="textareaMsg" name="inputTextarea" placeholder="Add multiple lines messages here..."></textarea>
            </div> -->
           
            <div class="checkbox" title="Checkboxes">
                <!-- <h3>Checkbox</h3>
                <div>
                    <label for="checkbox">{{ checked }}</label>
                    <input type="checkbox" name="checkbox" id="checkbox" v-model="checked" />
                </div> -->
                
                <div title="Checked Names">
                    <!-- Array containing names when chcked -->
                    <!-- <div>Checked names: {{ checkedNames }}</div>
                    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
                    <label for="jack">Jack</label>

                    <input type="checkbox" id="john" value="John" v-model="checkedNames" />
                    <label for="john">John</label>

                    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
                    <label for="mike">Mike</label> -->
                </div>

                <!-- <div title="Yes or No">
                    <label for="trueFalseCheckbox">Toggle</label>
                    <input type="checkbox" id="trueFalseCheckbox"
                        v-model="toggleYesNo" true-value="Yes" false-value="No"
                    >
                    &NonBreakingSpace;<span>{{ toggleYesNo }} </span>
                </div>

                <div title="Dynamic Yes or Dynamic No">
                    <label for="trueFalseCheckbox">Toggle2</label>
                    <input type="checkbox"
                        v-model="toggleDynamicTrueFalse"
                        true-value="dynamicTrueValue" false-value="dynamicFalseValue"
                    >
                    &NonBreakingSpace;<span>{{ toggleDynamicTrueFalse }} </span>
                </div>                   -->
            </div>

            <!-- <div class="radio" title="Radio Input Field">
                <h3>Radio</h3>
                <div>
                    <div>Picked: {{ picked }}</div>

                    <input type="radio" id="one" value="One" v-model="picked" />
                    <label for="one">One</label>
                    <input type="radio" id="two" value="Two" v-model="picked" />
                    <label for="two">Two</label>
                </div>
            </div> -->

            <div class="select" title="Selections">
                <!-- <h3>Select</h3>
                <div>
                    <p>Selected: {{ selected }}</p>

                    <select v-model="selected">
                        <option disabled value="">Please Select one</option>
                        <option>A</option>
                        <option>B</option>
                        <option>C</option>
                    </select>
                </div>
                <div title="Multiple">
                    <p>SelectedMultple: {{ selectedMultiple }}</p>
                    <select v-model="selectedMultiple" multiple id="selectedMultiple">
                        <option disabled value="">You may select more than one option</option>
                        <option>A</option>
                        <option>B</option>
                        <option>C</option>
                    </select>
                </div>
                <div>
                    <select v-model="selectedTable">
                        <option v-for="option in options" :value="option.value" :key="option">
                            {{ option.text }}
                        </option>
                    </select>
                </div>
                <div>  -->
                    <!-- inline object literal -->
                    <!-- <select v-model="selectedNumber">
                        <option :value="{ number: 123 }">123</option>
                    </select>
                </div> -->
            </div> 
        </div>

        <div class="row" title="Lifecycle Hooks">
            <!-- <h2>Lifecycle Hooks</h2>
            <p>Each Vue component instance goes through a series of initialization steps when it's created - for example, it needs to set up data observation, compile the template, mount the instance to the DOM, and update the DOM when data changes. Along the way, it also runs functions called lifecycle hooks, giving users the opportunity to add their own code at specific stages.</p> -->
        </div>

        <div class="row" title="Template Refs">
            
        </div>
        

        
    </div>
</template>

<style scoped>
    .container {
        display: grid;
        grid-template-columns: 1fr;
        padding-bottom: 6rem;
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

    input[type=text],
    input[type=number] {
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

    textarea {
        box-sizing: border-box;
        width: 70%;
        height: 100px;
        padding: 12px 20px;
        border: 1px solid #555;
        outline: none;
        border-radius: 4px;
        font-family: inherit;
        background-color: var(--color-background);
        color: #ddd;
        resize: both;       
        margin: 8px 0;
        transition: all 0.2s ease-out;
    }

    input[type=text]:focus,
    input[type=number]:focus,
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

    .checkbox input[type=checkbox],
    input[type=radio] {
        height: 16px;
        width: 16px;
        margin: 4px 0;
        transition: all 0.5s ease-in-out;
    }

    .checkbox label,
    .radio label {
        font-weight: 600;
        padding: 4px 20px 4px;
    }

    .select > div {
        margin: 1rem 0;
    }

    .select select {
        width: 70%;
        height: 40px;
        padding: 0.6rem 1.2rem;
        border: 1px solid #555;
        border-radius: 4px;
        background-color: var(--color-background);
        transition: all 0.3s ease-out;
    }

    .select #selectedMultiple {
        height: 120px;
    }

    .select option {
        padding: 8px 0;
    }
</style>