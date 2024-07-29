
<script setup>
    import IconTooling from './icons/IconTooling.vue'
</script>

<template>
    <div>
        <button type="submit" class="fancyBtn">
            <!-- Slot outlet -->
            <i>
                <IconTooling name="plus" /> 
            </i>  
            <span>
                <slot>Submit</slot>
            </span>        
        </button>

       
    </div>
</template>



<style scoped>
    .fancyBtn {
        border: none;
        outline: none;
        width: 150px;
        height: 40px;
        margin: 8px 0;
        text-align: center;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        border-radius: 22px 8px;
        background-color: var(--vt-c-black-mute);
        box-shadow: 2px 2px 1px 1px var(--vt-c-black), -2px -2px 1px 1px var(--vt-c-black);
    }

    .fancyBtn:active {
        transform: scale(0.95);
    }

    i {
        margin-right: 8px;
    }

    span {
        color: red;
    }
</style>