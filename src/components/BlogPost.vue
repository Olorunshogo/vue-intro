<script setup>
    const props = defineProps(['title', 'index', 'id'])

    const emit = defineEmits(['enlarge-text'])
    emit('enlarge-text')
</script>

<template>
    <div>
        <header>
            <h4>{{ props.index }}. {{ props.title }}</h4>
        </header>
        <main class="blog-post">
            <div class="textareaContainer">
                <textarea></textarea>
            </div>
            <div class="btnWrapper">
                <button class="btn">Send</button>
                <button class="btn" v-on:click="$emit('enlarge-text')">
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