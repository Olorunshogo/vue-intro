
<script setup>
import { ref } from 'vue'
    import FancyButton from './FancyButton.vue'
    import BaseLayout from './BaseLayout.vue'

    const message = ref('')
</script>

<template>
    <div>
        <FancyButton>
            Click Me!  
            <!-- Slot content -->
        </FancyButton>
        
        <FancyButton>
            Button!  
            <!-- Slot content -->
        </FancyButton>

        <FancyButton />

        <FancyButton>
            Save
        </FancyButton>

        <span>{{ message }}</span>
       <FancyButton>{{message}}</FancyButton>
       <input type="text" v-model="message" />
    </div>

    <div>
        <BaseLayout>
            <template v-slot:header>
                <h1>Here might be a page title</h1>
            </template>

            <!-- Implicit default slot -->
            <p>A paragraph for the main content</p>
            <p>Another paragraph</p>

            <template #footer>
                <h1>Here's some contact info</h1>
            </template>
        </BaseLayout>

    </div>
</template>



<style scoped>
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

    .meta {
        font-size: 0.8em;
        color: #42b883;
    }
</style>