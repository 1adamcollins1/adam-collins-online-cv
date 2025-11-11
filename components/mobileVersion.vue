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
          class="w-full h-full absolute flex z-40 pointer-events-none text-black overflow-hidden"
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
          <div class="relative w-full h-full flex flex-col p-4">
            <AboutMe
              @click="toggleTitle()"
              :pin-title="pinTitle"
              :pin-title-children="pinTitleChildren"
              :class="pinTitleChildren ? 'z-20' : 'z-40'"
            />
            <div class="h-[20%]"></div>
            <div 
              class="h-[60%] text-center flex justify-center items-center flex-col pb-12 px-4"
              :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
            >
              <img src="../public/images/profilepic.png" alt="" class="w-32 h-44">
              <br/>
              <p class=" text-[14px] md:text-[15px]">
                I am a personable Front-End Developer with over 5 years of experience building modern, scalable web and mobile applications. I have contributed to all stages of development from concept and testing to final delivery, providing value across the board. From B2B projects, agency work, start ups, etc. I can easily adapt to diverse work environments.
              </p>
            </div>
          </div>
          <div class="absolute z-30 h-full w-full flex flex-col-reverse p-4">
            <p 
              class="text-[#e4f1fe] font-bold transition-[height] duration-500 text-2xl bg-[#8dc6ff] h-[5%]"
              :class="activeSection === 'contactMe' ? 'h-[70%]' : 'h-[5%]'"
              @click="activeSection === 'contactMe' ? activeSection= '' : activeSection= 'contactMe'"
            >
            Contact Me
          </p>
            <p 
              class="text-[#e4f1fe] font-bold transition-[height] duration-500 text-2xl bg-[#8dc6ff] h-[5%]"
              :class="activeSection === 'education' ? 'h-[70%]' : 'h-[5%]'"
              @click="activeSection === 'education' ? activeSection= '' : activeSection= 'education'"
            >
              Education
            </p>
            <p 
              class="text-[#e4f1fe] font-bold transition-[height] duration-500 text-2xl bg-[#8dc6ff] h-[5%]"
              :class="activeSection === 'skills' ? 'h-[70%]' : 'h-[5%]'"
              @click="activeSection === 'skills' ? activeSection= '' : activeSection= 'skills'"
            >
              Skills
            </p>
            <p 
              class="text-[#e4f1fe] font-bold transition-[height] duration-500 text-2xl bg-[#8dc6ff]"
              :class="activeSection === 'experience' ? 'h-[70%]' : 'h-[5%]'"
              @click="activeSection === 'experience' ? activeSection= '' : activeSection= 'experience'"
            >
              Experience
            </p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { onMounted, onBeforeUnmount } from 'vue'
  import AboutMe from '~/components/cvSection/aboutMe.vue'
  
  const hideOverlay = ref(false)
  
  const peekRight = ref(false)
  const peelRight = ref(false)
  const pinTitle = ref(false)
  const shiftCvLeft = ref(false)
  const pinTitleChildren = ref(false)
  const pinTitleChildrenTwo = ref(false)
  const activeSection = ref(false)
  
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
  