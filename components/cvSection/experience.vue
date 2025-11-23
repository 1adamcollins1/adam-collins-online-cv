<template>   
    <div 
        v-bind="$attrs"
        ref="educationCont"
        class="h-fit md:h-full overflow-scroll"
        @scroll="handleLineUpScroll()"
    >
        <!-- <Icon
            v-if="showArrow"
            name="ic:round-keyboard-arrow-down" 
            class="text-[#22313f] absolute bottom-1 right-1 text-5xl"
        /> -->
        <h2 
            v-if="!hideHeader" 
            class="py-4 sticky top-0 bg-[#8dc6ff] text-[#e4f1fe] font-bold text-4xl z-10"
        >Experience</h2>
        <h3 class="font-bold">Front-End Developer</h3>
        <p >Urban Zoo</p>
        <p >Apr. 2025 – Oct. 2025 | <span class="italic">Warrington, UK</span></p>
        <ul class="list-disc pl-5">
            <li>Worked on an in-house CMS, creating websites for 30+ clients using <span class="text-skill" :class="{ highlighted: isHighlighted('nuxtJS') }">Nuxt.js</span> <span class="text-skill" :class="{ highlighted: isHighlighted('vueJS') }">(Vue.js)</span>, <span class="text-skill" :class="{ highlighted: isHighlighted('tailwind') }">Tailwind</span> and <span class="text-skill" :class="{ highlighted: isHighlighted('typescript') }">TypeScript</span>.</li>
            <li>Worked closely with Design and Back-End, taking complex <span class="text-skill" :class="{ highlighted: isHighlighted('figma') }">Figma designs</span>, creating <span class="text-skill" :class="{ highlighted: isHighlighted('restAPIs') }">REST API’s</span> and transforming data to make web-pages and re-usable components.</li> 
            <li>Led Front-End delivery for major projects such as National Leagues new live match center and site re-brands.</li> 
            <li>Worked in a fast-paced agile team, managing <span class="text-skill" :class="{ highlighted: isHighlighted('jira') }">Jira tickets</span> and urgent client requests.</li> 
        </ul>
        <br/>

        <h3 class="font-bold">Front-End Developer</h3>
        <p >Juicy Media</p>
        <p >Jun. 2023 – Mar. 2025 | <span class="italic">Manchester, UK</span></p>
        <ul class="list-disc pl-5">
            <li>Client-facing role creating websites, web applications and mobile apps in a self-driven work environment.</li>
            <li>Broad Front-End tech stack including <span class="text-skill" :class="{ highlighted: isHighlighted('reactNative') }">React Native</span>, <span class="text-skill" :class="{ highlighted: isHighlighted('vueJS') }">Vue.JS</span>, <span class="text-skill" :class="{ highlighted: isHighlighted('nuxtJS') }">Nuxt.JS</span>, and <span class="text-skill" :class="{ highlighted: isHighlighted('tailwind') }">WordPress</span>.</li> 
            <li>The principal developer and <span class="text-skill" :class="{ highlighted: isHighlighted('projectManagement') }">point of contact</span> for the client for the development of a web application used by council members, electoral candidates and the civil service for the last Police and Crime Commissioner election.</li> 
        </ul>
        <br/>

        <h3 class="font-bold">UX Developer</h3>
        <p >Macro 4</p>
        <p >Nov. 2021 – Jun. 2023 | <span class="italic">Manchester, UK</span></p>
        <ul class="list-disc pl-5">
            <li>Primarily involved in the designing and coding of web-based applications for an in-house product in <span class="text-skill" :class="{ highlighted: isHighlighted('typescript') }">TypeScript</span> alongside <span class="text-skill" :class="{ highlighted: isHighlighted('scss') }">SCSS</span>.</li>
            <li>Designed and developed a lightweight and low code Website builder.</li> 
            <li>Researched and used <span class="text-skill" :class="{ highlighted: isHighlighted('Grafana') }">Grafana</span> alongside <span class="text-skill" :class="{ highlighted: isHighlighted('graphQL') }">GraphQL</span> to create dashboards for the company metrics.</li> 
        </ul>
        <br/>

        <h3 class="font-bold">QA Tester</h3>
        <p >Rebellion Pay</p>
        <p >Sept. 2019 – Jun. 2020| <span class="italic">Madrid, Spain</span></p>
        <ul class="list-disc pl-5">
            <li>The <span class="text-skill" :class="{ highlighted: isHighlighted('qaTesting') }">sole tester</span> for all new features added to the Rebellion Pay Fintech App which had an <span class="text-skill">active user base of around 250,000</span>.</li>
            <li>Oversaw and managed the development flow using <span class="text-skill" :class="{ highlighted: isHighlighted('gitlab') }">GitLab Issue Boards</span> to organise the development sprints.</li> 
            <li>Required relocation to Madrid and the rapid learning of <span class="text-skill">basic Spanish to assist in translations</span> for press releases, notifications and in-app features.</li> 
        </ul>
        <br/>

        <h3 class="font-bold">Full-stack Developer</h3>
        <p >Beautiful Canoe</p>
        <p >Jun. 2019 – Aug. 2019 | <span class="italic">Birmingham, UK</span></p>
        <ul class="list-disc pl-5">
            <li>A three month placement as a full stack developer and project manager.</li>
            <li>Responsibilities included <span class="text-skill" :class="{ highlighted: isHighlighted('projectManagement') }">running client meetings</span>, gathering requirements and <span class="text-skill" :class="{ highlighted: isHighlighted('Grafana') }">managing workflow timelines</span>.</li> 
            <li>Tech stack was mostly <span class="text-skill" :class="{ highlighted: isHighlighted('projectManagement') }">PHP</span> and <span class="text-skill" :class="{ highlighted: isHighlighted('projectManagement') }">Laravel</span>.</li> 
        </ul>
        <br/>
    </div>
</template>

<script setup lang="ts">
interface Props {
    hideHeader?: boolean
}

defineProps<Props>()
import { ref } from 'vue'

const highlightedSkill = ref()
const educationCont = ref()
const showArrow = ref(true)

function isHighlighted(skill: any) {
  return highlightedSkill.value === skill
}

function handleLineUpScroll() {
    const el = (educationCont.value) 
    const scrollTop = el.scrollTop
    const scrollHeight = el.scrollHeight
    const clientHeight = el.clientHeight

    if (scrollTop + clientHeight + 30 >= scrollHeight) {
        showArrow.value = false
    }
    else{
        showArrow.value = true
    }
}
</script>