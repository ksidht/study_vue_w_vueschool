<!-- https://dev.to/caio2k/working-with-v-model-in-vue-3-3791 -->
<template>
  <div>
    View Model
    <label class="block">Text Area</label>

    <SidTextArea v-model="sidTextAreaRef" />

    <input v-model="sidInput" class="border border-slate-200">

    <p>Hello {{ sidInput }}</p>
    <p>Textarea {{ sidTextAreaRef }}</p>

  </div>
</template>

<script setup>
  import { ref } from "vue";
  import SidTextArea from "../components/Vmodel/SidTextArea.vue";


  const sidInput = ref('')
  const sidTextAreaRef = ref('')

</script>