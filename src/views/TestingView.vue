<script setup>
    import { ref } from 'vue'

    // import InputFields from '../components/InputFields.vue'

    

    // COMPONENTS
    // import CounterComp from '../components/CounterComp.vue'
    // import BlogPost from '../components/BlogPost.vue'
    // import AdCount from '../components/AdCount.vue' 
    import AlertBox from '../components/AlertBox.vue'
    // import Slot from '../components/Slots.vue'

    // const posts = ref([
    //     { index: 1, id: 'textareaOne', title: "My journey with Vue", greetingMessage: "1. Hello Vue!!!" },
    //     { index: 2, id: 'textareaTwo', title: "Blogging with Vue", greetingMessage: "2. Hello Vue!!!" },
    //     { index: 3, id: 'textareaThree', title: "Why Vue is so much fun", greetingMessage: "3. Hello Vue!!!" }
    // ])
    // const postFontSize = ref(1)

    

    

</script>

<template>
    <div class="container">
        <header class="header" title="Header">
            <h1>TESTING VIEW</h1>
        </header>

        <div class="row" title="Component Basics">
            <h3>Component Basics</h3>

            <!-- === COUNTER COMPONENT === -->
            <!-- <div>
                <b>Here is a child component!</b>

                <CounterComp title="The First Counter Component" />
                <CounterComp title="The Second Counter Component" />  
            </div>     -->
            <!-- === BLOGPOST COMPONENT === -->
            <!-- <div v-bind:style="{ fontSize: postFontSize + 'em' }">
                <BlogPost 
                    v-for="post in posts"
                    v-bind:key="post"
                    v-bind:title="post.title"
                    v-bind:index="post.index"
                    v-bind:greetingMessage="post.greetingMessage"
                    @enlarge-text="postFontSize += 0.1"
                />
            </div>    -->
            <!-- === ALERTBOX COMPONENT === -->
            <div>
                <AlertBox />
            </div>
            <!-- <div>
                <AdCount :initial-value="0" increment="5" decrement="2"/>
                <AdCount :initial-value="4" increment="4" decrement="1"/>
            </div> -->
        </div>

        <!-- <div title="Component V-Model">
            <div>
                <InputFields  />
            </div>
        </div> -->
        

        
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

    

    

    
</style>