<script setup>
import { ref } from "vue";

const count = ref(0)

// console.log(count)

</script>

<template>
    <button @click="count++">Increase</button>
    <div>{{ count }}</div>
</template>