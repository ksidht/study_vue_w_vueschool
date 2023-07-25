<script setup>
import { ref } from "vue";
import PostInput from "./PostInput.vue";

defineProps(['post'])
const emit = defineEmits(['enlarge-text'])
const postinput = ref("Hello")
</script>

<template>
  <div class="group relative mt-4 px-4  py-2 rounded-3xl ring-1 ring-gray-200 ">
    <h3 class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600">
      <a href="#">
        <span class="absolute inset-0" />
        {{ post.title }}
      </a>
    </h3>
    <p class="mt-5 line-clamp-3 text-sm leading-6 text-gray-600"><slot></slot></p>
  </div>

  <button @click="emit('enlarge-text')">Enlarge text</button>

  <PostInput v-model:postinput="postinput"/>

  {{ postinput }}


</template>