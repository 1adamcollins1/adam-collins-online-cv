<template>
    <div class="border-3 box-border border-black/50 border-dashed bg-amber-200">
        <div class="w-full h-20 bg-black/10"></div>
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