<template>  
    <div>
        <h2
            v-if="!hideHeader" 
            class="text-[#e4f1fe] font-bold text-4xl "
        >Skills</h2>
        <div class="w-full overflow-scroll flex-1 pb-4">
            <h3 class="font-bold">Languages</h3>
            <p>TypeScript, Vue.js, ReactJS, React Native, Nuxt.js, HTML5, JavaScript, CSS, SCSS, SASS, Node.js, WordPress, GraphQL, SQL</p>
        
            <h3 class="font-bold">Development</h3>
            <p>SCRUM, Agile, GitLab Boards, Jira, Project Management, Client Communication, Project Presentation</p>
        
            <h3 class="font-bold">Technologies</h3>
            <p>Docker, Figma, Postman, FileZilla, Siteground, Git CLI, Github, REST API’s, GitLab management, Fintech, Pinia, Expo</p>
        </div>
    </div>
</template>

<script setup lang="ts">
interface Props {
    hideHeader?: boolean
}

defineProps<Props>()
</script>