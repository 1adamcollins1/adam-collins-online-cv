<template>
  <div class="relative w-96 h-96 border border-gray-300">
    <ClientOnly>
      <Peel drag :peel-position="{ x: 120, y: 120 }">
        <template #top>
          <div class="layer w-full h-full flex items-center justify-center bg-red-400 text-white">
            Top
          </div>
        </template>

        <template #back>
          <div class="layer w-full h-full flex items-center justify-center bg-green-400 text-white">
            Back
          </div>
        </template>

        <template #bottom>
          <div class="layer w-full h-full flex items-center justify-center bg-blue-400 text-white">
            Bottom
          </div>
        </template>
      </Peel>
    </ClientOnly>
  </div>
</template>


<script setup>
import Peel from 'vue-peel'
import 'vue-peel/style.css'
</script>
