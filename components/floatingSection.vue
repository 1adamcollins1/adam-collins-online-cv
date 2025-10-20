<template>
    <div class="p-2 bg-white">
        <p class=" text-2xl">{{ title }}</p>
        <slot></slot> 
    </div>
</template>

<script setup lang="ts">
interface Props {
    title?: string
}

defineProps<Props>()
</script>