<template>
  <div class="h-dvh w-[133%] relative flex flex-row transition-all duration-500"
    :class="shiftCvLeft ? 'left-[-33.3%]' : 'left-0'"
  >
    <div 
      class="flex absolute bottom-4 left-4 bg-[#8dc6ff] h-10 w-10 rounded-full z-50 items-center justify-center"
      @click="revealContent()"
    >
      <Icon 
        name="mdi:play" 
        class="text-white  text-5xl "
      />
    </div>
    <div class="relative h-full w-screen">
      <div 
      class="absolute inset-0 p-4 left-1/2 transform -translate-x-1/2 -translate-y-1/2  w-[28%] h-[15%] z-50 flex flex-col justify-between items-center translate-all duration-500"
        :class="pinTitle ? 'top-[7.5%]' : 'top-1/2', pinTitleChildren ? '' : 'text-[#8dc6ff]'"
        @click="toggleTitle()"
      >
        <p 
          class="translate-all duration-500 font-medium"
          :class="pinTitleChildren ? 'text-5xl' : 'text-4xl'"
        >
          Adam Collins
        </p>
        <div 
          class="rounded-3xl h-1 bg-[#34495e] translate-[width] duration-500"
          :class="pinTitleChildren ? 'w-full ' : 'w-0'"
        />
        <p 
          class="text-[0.8rem] translate-all duration-500 text-center"
          :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
        >
          +44 7592738027 | adamcollins31@gmail.com
        </p>
      </div>
      <!-- <div class="absolute inset-0  top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  w-80 h-60 z-50 flex justify-center items-center text-2xl">
        <p>Adam Collins</p>
      </div> -->
      <!-- OVERLAY -->
      <div 
        class="w-full h-full absolute flex z-20 pointer-events-none text-black overflow-hidden"
        :class="{'hidden' : hideOverlay}"
      >
        <div 
          class="absolute right-0 w-20 h-full pointer-events-auto"
          :class="[peelRight ? 'pointer-events-none' : '']" 
          @mouseover="peekRight=true" 
          @mouseleave="peekRight=false" 
          @click="peelRight = !peelRight"
        ></div> 
        <div 
          class="w-[35%] h-full bg-[#34495e] pointer-events-auto"
          @click="shiftCvLeft = !shiftCvLeft"
        >
        </div>
        <div 
          class="w-[30%] bg-[#34495e] pointer-events-auto transition-all duration-500"
          :class="!pinTitleChildren ? 'translate-y-0 opacity-100' : 'translate-y-full opacity-0'"
        >
        </div>
        <div 
          class="h-full bg-[#34495e] transition-[width] duration-500"
          :class="{
            'w-0': peelRight,
            'w-[33%]': peekRight && !peelRight,
            'w-[35%]': !peekRight && !peelRight
          }"
        >
        </div>
      </div>
      <!-- CONTENT -->
      <div class="w-full h-full absolute flex overflow-hidden">
        <div class="relative w-[35%] h-full">
        </div>
        <div class="relative w-[30%] h-full flex flex-col p-4">
          <div class="h-[15%]"></div>
          <div 
            class="h-fit text-center flex justify-center items-center flex-col pb-4"
            :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
          >
            <img src="../public/images/profilepic.png" alt="" class=" w-32 h-44">
            <br/>
            <p>Front-End Developer skilled in modern frameworks, creating scalable, pixel-perfect web and software applications.</p>
          </div>
          <div class="absolute bottom-0 pb-4 flex-1">
            <div class="absolute top-[-3px] left-0 w-full h-full top-fade transition-all duration-1000"
              :class="!pinTitleChildrenTwo ? 'translate-y-0' : 'translate-y-full'"
            ></div>
            <h2 class="text-[#e4f1fe] font-bold text-4xl ">Skills</h2>
            <div>
              <h3 class="font-bold">Languages</h3>
              <p>TypeScript, Vue.js, ReactJS, React Native, Nuxt.js, HTML5, JavaScript, CSS, SCSS, SASS, Node.js, WordPress, GraphQL, SQL</p>
            </div>
            <div>
              <h3 class="font-bold">Development</h3>
              <p>SCRUM, Agile, GitLab Boards, Jira, Project Management, Client Communication, Project Presentation</p>
            </div>
            <div>
              <h3 class="font-bold">Technologies</h3>
              <p>Docker, Figma, Postman, FileZilla, Siteground, Git CLI, Git Version Control, REST API’s, GitLab management, Fintech</p>
            </div>
          </div>
        </div>
        <div 
          class="h-full w-[35%] p-4 pt-0 overflow-scroll transition-[opacity] duration-500"
          :class="peelRight ? 'opacity-100' : 'opacity-0'"
        >
          <cv-section-experience/>
        </div>
      </div>
    </div>
    <div class="w-[33vw] h-full p-4 overflow-scroll">
      <cv-section-education/> 
      <div class="absolute bottom-0 right-0  p-4">
        <cv-section-contact-me/>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount } from 'vue';

import 'vue-peel/style.css'


const hideOverlay = ref(0)

// const peekRight = ref(1)
// const peelRight = ref(1)
// const pinTitle = ref(1)
// const shiftCvLeft = ref(1)
// const pinTitleChildren = ref(1)
// const pinTitleChildrenTwo = ref(1)

const peekRight = ref(0)
const peelRight = ref(0)
const pinTitle = ref(0)
const shiftCvLeft = ref(0)
const pinTitleChildren = ref(0)
const pinTitleChildrenTwo = ref(0)

function toggleTitle() {
  pinTitle.value = true

  if(pinTitle.value){
    setTimeout(() => {
      pinTitleChildren.value = true
    }, 300)
    setTimeout(() => {
      pinTitleChildrenTwo.value = true
    }, 600)
  }
  else {
    pinTitleChildren.vlaue = false
  }
}

function revealContent(){
  peelRight.value = true
  setTimeout(() => {
      pinTitle.value = true
  }, 500)
  setTimeout(() => {
      pinTitleChildren.value = true
  }, 1000)
  setTimeout(() => {
    pinTitleChildrenTwo.value = true
  }, 1600)
  setTimeout(() => {
    shiftCvLeft.value = true
  }, 2100)
}

onMounted(() => {
})

onBeforeUnmount(() => {
})
</script>
