<template>  
    <div>
        <h2
            v-if="!hideHeader" 
            class="text-[#e4f1fe] font-bold text-4xl "
        >Skills</h2>
        <div class="w-full overflow-scroll flex-1 pb-4">
            <h3 class="font-bold">Languages</h3>
            <p>TypeScript, Vue.js, ReactJS, React Native, Nuxt.js, Next.js, PHP, Node.js HTML5, JavaScript, CSS, SCSS, Tailwind, Bootstrap, Node.js, WordPress, GraphQL, SQL, Pina</p>
        
            <h3 class="font-bold">Development</h3>
            <p>SCRUM, Agile, Jira, Project Management, Client Communication, Project Presentation, QA Testing, UX/UI Design</p>
        
            <h3 class="font-bold">Technologies</h3>
            <p>Docker, Figma, Postman, FileZilla, Siteground, Git CLI, Git Version Control, REST API's,  GitLab management, Jira, Fintech, Google Analytics, Firebase, Cloudflare</p>
        </div>
    </div>
</template>

<script setup lang="ts">
interface Props {
    hideHeader?: boolean
}

defineProps<Props>()
</script>