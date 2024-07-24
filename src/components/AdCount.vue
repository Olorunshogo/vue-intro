
<script setup>

import { ref } from 'vue'

const props = defineProps({
  increment: Number,
  decrement: Number,
  initialValue: Number
})

const currentValue = ref(props.initialValue)
// OR
// const props = withDefaults(defineProps<Props>(), {
//   initialValue: 0
// })

function doDecrement() {
  currentValue.value -= props.decrement
}

function doIncrement() {
  currentValue.value += props.increment
}

</script>

<template>
    <div>
        <p>Current Value: {{ currentValue }}</p>
        <button @click="doIncrement">Increment by {{ increment }}</button>
        <button @click="doDecrement">Decrement by {{ decrement }}</button>
    </div>
</template>



<style lang="scss" scoped>

</style>