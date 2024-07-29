
<script setup>


    
</script>

<template>
    <div class="card">
        <div v-if="$slots.header" class="card-head">
            <header>
                <slot name="header"></slot>
            </header>
        </div>

        <div v-if="$slots.default" class="card-container">
            <main>
                <slot></slot>
            </main>
        </div>

        <div v-if="$slots.footer" class="card-footer">
            <footer>
                <slot name="footer"></slot>
            </footer>
        </div>
    </div>
</template>

<style scoped>

</style>