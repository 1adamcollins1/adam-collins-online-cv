<template>
    <div class="h-dvh w-screen relative flex flex-row transition-all duration-500"
      :class="shiftCvLeft ? 'left-[-33.3%]' : 'left-0'"
    >
      <div class="relative h-full w-screen">
        
        <!-- <div class="absolute inset-0  top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  w-80 h-60 z-50 flex justify-center items-center text-2xl">
          <p>Adam Collins</p>
        </div> -->
        <!-- OVERLAY -->
        <div 
          class="w-full h-full absolute flex z-20 pointer-events-none text-black overflow-hidden"
          :class="{'hidden' : hideOverlay}"
        >
          <div 
            class="w-screen bg-[#34495e] pointer-events-auto transition-all duration-500"
            :class="!pinTitleChildren ? 'translate-y-0 opacity-100' : 'translate-y-full opacity-0'"
          >
          </div>
        </div>
        <!-- CONTENT -->
        <div class="w-full h-full absolute flex overflow-hidden">
          <div class="relative w-full h-full flex flex-col px-4 pt-4">
            <AboutMe
              @click="toggleTitle()"
              :pin-title="pinTitle"
              :pin-title-children="pinTitleChildren"
            />
            <div class="h-[15%]"></div>
            <div 
              class="h-[40%] text-center flex justify-center items-center flex-col pb-4"
              :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
            >
              <img src="../public/images/profilepic.png" alt="" class="w-28 h-36 md:w-32 md:h-44">
              <br/>
              <p class=" text-[14px] md:text-[16px]">Front-End Developer skilled in modern frameworks, creating scalable, pixel-perfect web and software applications.</p>
            </div>
            <div class="h-[45%] w-full flex flex-col justify-between">
              <h2 class="text-[#e4f1fe] font-bold text-4xl ">Experience</h2>
              <h2 class="text-[#e4f1fe] font-bold text-4xl ">Skills</h2>
              <h2 class="text-[#e4f1fe] font-bold text-4xl ">Education</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { onMounted, onBeforeUnmount } from 'vue'
  import AboutMe from '~/components/cvSection/aboutMe.vue'
  
  const hideOverlay = ref(false)
  
  // const peekRight = ref(1)
  // const peelRight = ref(1)
  // const pinTitle = ref(1)
  // const shiftCvLeft = ref(1)
  // const pinTitleChildren = ref(1)
  // const pinTitleChildrenTwo = ref(1)
  
  const peekRight = ref(false)
  const peelRight = ref(false)
  const pinTitle = ref(false)
  const shiftCvLeft = ref(false)
  const pinTitleChildren = ref(false)
  const pinTitleChildrenTwo = ref(false)
  
  function toggleTitle() {
    pinTitle.value = true
    setTimeout(() => pinTitleChildren.value = true, 300)
    setTimeout(() => pinTitleChildrenTwo.value = true, 600)
  }
  
  function revealContent(){
    peelRight.value = true
    setTimeout(() => { pinTitle.value = true }, 500)
    setTimeout(() => { pinTitleChildren.value = true }, 1000)
    setTimeout(() => { pinTitleChildrenTwo.value = true }, 1600)
    setTimeout(() => { shiftCvLeft.value = true }, 2100)
  }
  
  onMounted(() => {
  })
  
  onBeforeUnmount(() => {
  })
  </script>
  