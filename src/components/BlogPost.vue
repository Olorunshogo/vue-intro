<script setup>
    const props = defineProps({
        title: String,
        id: Number,
        index: Number,
        greetingMessage: String
    })

    // defineEmits(['enlargeText', 'inFocus'])
    // const emit = defineEmits({
    //     // No validation
    //     click: null,

    //     // Validate submit event
    //     submit: ({ email, password }) => {
    //         if (email && password) {
    //             return true
    //         } else {
    //             console.warn('Invalid submit event payload!')
    //             return false
    //         }
    //     }
    // })

    // function submitForm(email, password) {
    //     emit('submit', { email, password })
    // }
    

    // PROPS TYPES
    // defineProps({

    //     Basic type check
    //      (`null` and `undefined` values will allow any type)
    //     propA: Number,

    //     // Multiple possible types
    //     propB: [String, Number],

    //     // Required string
    //     propC: {
    //         type: String,
    //         required: true
    //     },

    //     // Required but nullable string
    //     propD: {
    //         type: [String, null],
    //         required: true
    //     },

    //     // Number with a default value
    //     propE: {
    //         type: Number,
    //         default: 100
    //     },

    //     // Object with a default value
    //     propF: {
    //         type: Object,
    //         // Object or array defaults must be returned from
    //         // a factory function. The function receives the raw
    //         // props received by the component as the argument.
    //         default(rawProps) {
    //         return { message: 'hello' }
    //         }
    //     },

    //     // Custom validator function
    //     // full props passed as 2nd argument in 3.4+
    //     propG: {
    //         validator(value, props) {
    //         // The value must match one of these strings
    //         return ['success', 'warning', 'danger'].includes(value)
    //         }
    //     },

    //     // Function with a default value
    //     propH: {
    //         type: Function,
    //         // Unlike object or array default, this is not a factory
    //         // function - this is a function to serve as a default value
    //         default() {
    //         return 'Default function'
    //         }
    //     }
    // })

</script>

<template>
    <div>
        <header>
            <h4>{{ props.index }}. {{ props.title }}</h4>
        </header>
        <main class="blog-post">
            <p>{{ props.greetingMessage }}</p>
            <div class="textareaContainer">
                <textarea></textarea>
            </div>
            <div class="btnWrapper">
                <button class="btn">Send</button>
                <button class="btn" v-on:click="$emit('enlargeText')">
                    Enlarge text
                </button>
            </div>
        </main>
    </div>
</template>



<style scoped>
    header h4 {
        text-align: center;
        font-size: 1.6rem;
        font-weight: 600;
    }

    main {
        display: flex;
        flex-direction: column;
    }

    .textareaContainer {
        display: flex;
        justify-content: center;
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
        font-size: 1rem;
        background-color: var(--color-background);
        color: #ddd;
        resize: both;       
        margin: 8px 0;
        transition: all 0.2s ease-out;
    }

    textarea:focus {
        background-color: #333;
        width: 80%;
    }

    .btnWrapper {
        display: flex;
        width: 270px;
        justify-content: space-between;
        margin-left: auto;
    }

    .btn {
        border: none;
        outline: none;
        width: 130px;
        height: 40px;
        margin: 8px 0;
        font-size: 1.1rem;
        font-weight: 600;
        text-align: center;
        border-radius: 22px 8px;
        background-color: var(--vt-c-white-soft);
        box-shadow: 2px 2px 1px 1px var(--vt-c-white), -2px -2px 1px 1px var(--vt-c-white-mute);
    }
    .btn:active {
        transform: scale(0.95);
    }
</style>