<script setup>
const props = defineProps(['postinput'])
const emit = defineEmits(['update:postinput'])


function sidCalled() {
  emit('update:postinput', props.postinput+"1")
}

console.log(props)
</script>
<template>
  <input 
    :value="postinput"
    @input="$emit('update:postinput', $event.target.value)"
  />

  <button @click="sidCalled">Sid Called</button>

</template>