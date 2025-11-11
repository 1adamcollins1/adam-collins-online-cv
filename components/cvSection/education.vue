<template>   
    <section v-bind="$attrs">
        <h2 
            class="py-4 sticky top-0 bg-[#8dc6ff] text-[#e4f1fe] font-bold text-4xl z-10"
            v-if="!hideHeader"    
        >
            Education
        </h2>
        <h3 class="font-bold">BSc (Hons): Computer Science with Multimedia</h3>
        <p >Aston University</p>
        <p >2017 – Oct. 2021 | <span class="italic">Birmingham, UK</span></p>
        <ul class="list-disc pl-5">
            <li>Graded a 2.1.</li>
            <li>Achieved highly in a broard range of modules such as Multimedia Implementation, Graphical Information Systems, Artificial Intelligence Fundamentals, Database Management, Computer Animation and Cyber Security.</li> 
            <li>Received the Game of the Year and Team of the Year award, awarded by Aston''s Industry Club.</li> 
            <li>Recieved the federation Silver Award from Aston Student's Union for being the co-founder and Vice President of the Aston Drama society.</li>
        </ul>
        <br/>
    </section>
</template>

<script setup lang="ts">
interface Props {
    hideHeader?: boolean
}

defineProps<Props>()
</script>