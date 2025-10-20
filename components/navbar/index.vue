<template>
    <nav class="bg-blue-600 text-white p-4 w-full">
      <div class="w-fit relative">
        <h1 class="font-serif uppercase text-6xl text-white" :class="strikeThrough ? 'line-through' : ''">
          
        </h1>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  
  const props = defineProps({
    strikeThrough: {
      type: Boolean,
      default: false
    }
  })
  </script>
  