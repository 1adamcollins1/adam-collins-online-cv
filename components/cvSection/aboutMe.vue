<template>   
    <div 
        class="absolute inset-0 p-4 left-1/2 transform -translate-x-1/2 -translate-y-1/2  w-full h-[15%] flex flex-col justify-between items-center translate-all duration-500"
        :class="[
            pinTitle ? 'top-[7.5%]' : 'top-1/2',
            pinTitleChildren ? '' : 'text-[#8dc6ff]'
        ]"
    >
        <p 
            class="translate-all duration-500 font-bold md:font-medium"
            :class="pinTitleChildren ? 'lg:text-5xl md:text-4xl text-4xl' : 'lg:text-4xl md:text-3xl text-3xl'"
        >
            Adam Collins
        </p>
        <div 
            class="rounded-3xl h-1 bg-[#22313f] translate-[width] duration-500"
            :class="pinTitleChildren ? 'w-full ' : 'w-0'"
        />
        <p 
            class="text-[0.8rem] translate-all duration-500 text-center"
            :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
        >
            +44 7592738027 | adamcollins31@gmail.com
        </p>
    </div>
</template>

<script setup lang="ts">
interface Props {
    pinTitle: boolean,
    pinTitleChildren: boolean
}

defineProps<Props>()
</script>