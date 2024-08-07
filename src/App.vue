<script setup>
import { ref, computed } from 'vue';
import { marked } from 'marked';

const markdown = ref('# Hello, Markdown');

const compiledMarkdown = computed(() => marked(markdown.value));

</script>

<template>
  <div class="container mx-auto p-4 h-full flex flex-col">
    <h1 class="text-2xl font-bold mb-4">Markdown Previewer</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4 flex-grow">
      <textarea
        v-model="markdown"
        class="w-full h-full border p-2"
        placeholder="Enter Markdown here..."
      ></textarea>
      <div
        class="w-full h-full border p-2"
        v-html="compiledMarkdown"
      ></div>
    </div>
  </div>
</template>