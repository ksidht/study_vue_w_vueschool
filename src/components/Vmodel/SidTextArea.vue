<template>
  <textarea 
    class="border border-slate-200"
    @keyup="emit('update:modelValue', $event.target.value)"
    v-text="modalValue"
    ></textarea>
</template>



<script setup>

defineProps(['modelValue'])
let emit = defineEmits(['update:modelValue'])

</script>