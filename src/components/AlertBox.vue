
<script setup>
    import IconTooling from '../components/icons/IconTooling.vue'
</script>

<template>
    <div class="alert-box">
        <div class="tooling">
            <i>
                <IconTooling />
            </i>
        </div>
        <div class="alert-msg">
            <strong>This is an Error for Demo Purposes</strong>
            <!-- <p>Something bad happened.</p> -->
            <slot />
        </div>
    </div>
</template>



<style scoped>
    .alert-box {
        display: flex;
        flex-direction: row;
        flex: 0 0 100%;
        max-width: 100%;
        justify-content: space-between;
        background-color: #111;
        border: 1px solid rgb(246, 40, 60);
        border-radius: 8px;
        padding: 1.5rem 0.5rem;
    }

    .tooling  {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 15%;
        flex: 0 0 15%;
        padding: 0.5rem 1rem;
    }

    .tooling i {
        color: rgb(246, 40, 60);
    }

    .alert-msg {
        display: flex;
        flex-direction: column;
        max-width: 85%;
        flex: 0 0 85%;
    }

    .alert-msg strong {
        font-size: 1.3rem;
        font-weight: 600;
        color: rgb(246, 40, 60);
    }
    .alert-msg p {
        font-size: 1.2rem;
        font-weight: 600;
        color: #aaa;
    }
</style>