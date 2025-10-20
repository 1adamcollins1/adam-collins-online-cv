<template>
  <!-- OVERLAY -->
  <div class="h-dvh w-dvw absolute left-0 top-0 z-10 flex flex-row overflow-hidden p-1 gap-1 bg-white">
    <div class="w-1/2 h-full flex flex-col gap-1">
      <div class="h-[30%] w-full"> 
        <Peel
          drag
          style="height: 100%; width: 100%; display: block;"
          :peel-position="{ x: 10, y: 10 }"
          :options="{
            corner: corners.TOP_LEFT
          }"
          :constraints="[corners.BOTTOM_LEFT, corners.BOTTOM_RIGHT]"
        >
          <template #top>
            <CoverSection class="h-full w-full" title="About Me" />
          </template>
          <template #back>
            <FloatingSection class="w-full h-full rotate-180" title="">
              <h3 class="font-bold">BSc (Hons) Computer Science with Multimedia (with a year in Industry) </h3>
              <p >2017-2021 | Aston University</p>
              <ul class="list-disc pl-5">
                <li>Graduated with a 2.1.</li>
                <li>Received the Game of the Year and Team of the Year award, awarded by Aston’s Industry Club.</li> 
                <li>Federation Silver Award from Aston Students’ Union for being Vice President and co-founder of the Aston Drama society.</li> 
              </ul>
            </FloatingSection>
          </template>
          <template #bottom>
            <FloatingSection class="w-full h-full" title="Adam Collins">
              <p>+44 7592 738027 | adamcollins31@gmail.com | LinkedIn</p>
              <p>Front-End Developer skilled in modern frameworks, creating scalable, pixel-perfect web and software applications.</p>
              <p class=" text-2xl bottom-1.5 absolute">Education</p>
            </FloatingSection>
          </template>
        </Peel>
      </div>
      <div class="h-[30%] w-full p-0.5"> 
        <BackSection></BackSection>
      </div>
      <div class="h-[30%] w-full flex flex-row gap-1"> 
        <div class="h-full w-1/2"> 
        <Peel
          drag
          style="height: 100%; width: 100%; display: block;"
          :peel-position="{ x: 10, y: 10 }"
          :options="{
            corner: corners.TOP_LEFT
          }"
          :constraints="[corners.TOP_RIGHT, corners.BOTTOM_RIGHT]"
        >
          <template #top>
            <CoverSection class="h-full w-full" title="SKILLS" />
          </template>
          <template #back>
            <FloatingSection class="w-full h-full" title="">
              <h3 class="font-bold">Development</h3>
              <p >SCRUM, Agile, GitLab Boards, Jira, Project Management, Client Communication, Project Presentation</p>
              <h3 class="font-bold">Technologies</h3>
              <p>Docker, Figma, Postman, FileZilla, Siteground, Git CLI, Git Version Control, REST API’s, GitLab managem</p>
            </FloatingSection>
          </template>
          <template #bottom>
            <FloatingSection class="w-full h-full" title="">
              <h3 class="font-bold">Languages</h3>
              <p >TypeScript, Vue.js, ReactJS, React Native, Nuxt.js, HTML5, JavaScript, CSS, SCSS, SASS, Node.js, WordPress, GraphQL, SQL</p>
            </FloatingSection>
          </template>
        </Peel>
        </div>
        <div class="h-full w-1/2"> 
          <BackSection></BackSection>
        </div>
      </div>
      <div class="h-[10%] w-full flex flex-row gap-1"> 
        <div class="h-full w-1/2"> 
          <Peel
            drag
            style="height: 100%; width: 100%; display: block;"
            :peel-position="{ x: 10, y: 10 }"
            :options="{
              corner: corners.TOP_LEFT
            }"
            :constraints="[corners.TOP_RIGHT, corners.BOTTOM_RIGHT]"
          >
            <template #top>
              <CoverSection class="h-full w-full" title="References" />
            </template>
            <template #back>
              <FloatingSection class="w-full h-full" title="">
                <p>Available upon request </p>
                <a href="https://www.bbc.co.uk/news">contact me</a>
              </FloatingSection>
            </template>
            <template #bottom>
              <FloatingSection class="w-full h-full" title="">
                <h3 class=" text-2xl">References: </h3>
              </FloatingSection>
            </template>
          </Peel>
        </div>
        <div class="h-full w-1/2"> 
          <BackSection></BackSection>
        </div>
      </div>
    </div>
    <div class="w-1/2 h-1/2">
      <Peel
          drag
          style="height: 100%; width: 100%; display: block;"
          :peel-position="{ x: 10, y: 10 }"
          :options="{
            corner: corners.TOP_LEFT
          }"
          :constraints="[corners.BOTTOM_LEFT, corners.BOTTOM_RIGHT]"
        >
          <template #top>
            <CoverSection class="h-full w-full" title="Experience" />
          </template>
          <template #back>
            <FloatingSection class="w-full h-full rotate-180" title="">
            </FloatingSection>
          </template>
          <template #bottom>
            <FloatingSection class="w-full h-full overflow-scroll" title="Work Experience">
              <div class=" flex-1 overflow-scroll h-[90%]">
                <h3 class="font-bold">Urban Zoo</h3>
                <p >Apr. 2025 – Oct. 2025 | <span class="italic">Warrington, UK</span></p>
                <ul class="list-disc pl-5">
                  <li>Worked on an in-house CMS, creating websites for 30+ clients using Nuxt.js (Vue.js), Tailwind and TypeScript.</li>
                  <li>Worked closely with Design and Back-End, taking complex Figma designs, creating REST API’s and transforming data to
  make web-pages and re-usable components.</li> 
                  <li>Led Front-End delivery for major projects such as sporting dashboards for live matches and site re-brands.</li> 
                  <li>Worked in a fast-paced agile team, managing Jira tickets and urgent client requests.</li> 
                </ul>
                <br/>
                <h3 class="font-bold">Urban Zoo</h3>
                <p >Apr. 2025 – Oct. 2025 | <span class="italic">Warrington, UK</span></p>
                <ul class="list-disc pl-5">
                  <li>Worked on an in-house CMS, creating websites for 30+ clients using Nuxt.js (Vue.js), Tailwind and TypeScript.</li>
                  <li>Worked closely with Design and Back-End, taking complex Figma designs, creating REST API’s and transforming data to
  make web-pages and re-usable components.</li> 
                  <li>Led Front-End delivery for major projects such as sporting dashboards for live matches and site re-brands.</li> 
                  <li>Worked in a fast-paced agile team, managing Jira tickets and urgent client requests.</li> 
                </ul>
                <br/>
                <h3 class="font-bold">Urban Zoo</h3>
                <p >Apr. 2025 – Oct. 2025 | <span class="italic">Warrington, UK</span></p>
                <ul class="list-disc pl-5">
                  <li>Worked on an in-house CMS, creating websites for 30+ clients using Nuxt.js (Vue.js), Tailwind and TypeScript.</li>
                  <li>Worked closely with Design and Back-End, taking complex Figma designs, creating REST API’s and transforming data to
  make web-pages and re-usable components.</li> 
                  <li>Led Front-End delivery for major projects such as sporting dashboards for live matches and site re-brands.</li> 
                  <li>Worked in a fast-paced agile team, managing Jira tickets and urgent client requests.</li> 
                </ul>
              </div>
            </FloatingSection>
          </template>
        </Peel>
      </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount } from 'vue';
import Peel, { corners } from 'vue-peel'
import 'vue-peel/style.css'

onMounted(() => {
})

onBeforeUnmount(() => {
})
</script>
