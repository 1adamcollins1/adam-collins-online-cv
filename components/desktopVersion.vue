<template>
    <div class="h-dvh w-[133%] relative flex flex-row transition-all duration-500"
      :class="shiftCvLeft ? 'left-[-33.3%]' : 'left-0'"
    >
      <div 
        class="flex absolute bottom-4 left-4 bg-[#8dc6ff] h-10 w-10 rounded-full z-50 items-center justify-center"
        @click="revealContent()"
      >
        <Icon 
          name="ic:round-play-arrow" 
          class="text-white  text-5xl "
        />
      </div>
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
          <div class="relative w-[30%] h-full flex flex-col px-4 pt-4">
            <AboutMe
              @click="toggleTitle()"
              :pin-title="pinTitle"
              :pin-title-children="pinTitleChildren"
              class="z-40"
            />
            <div class="h-[15%]"></div>
            <div 
              class="h-[70%] text-center flex justify-between items-center flex-col pb-4 mx-8 overflow-scroll"
              :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
            >
              <img src="../public/images/profilepic.png" alt="" class="w-28 h-36 md:w-32 md:h-44">
              <br/>
              <p class=" text-[14px] md:text-[15px]">
                I am a personable Front-End Developer with over 5 years of experience building modern, scalable web and mobile applications. I have contributed to all stages of development from concept and testing to final delivery, providing value across the board. From B2B projects, agency work, start ups, etc. I can easily adapt to diverse work environments.
              </p>
              <p class=" text-[14px] md:text-[15px]">
                With a keen eye for pixel-perfect design and strong technical skills, I take pride in delivering seamless UX. Comfortable with public speaking and presentations, I thrive in fast-paced, AGILE environments. I enjoy bringing ideas to life efficiently and effectively, either by collaborating as a team or working solo.
              </p>
            </div>
          </div>
          <div 
            class="h-full w-[35%] px-4 overflow-scroll transition-[opacity] duration-500"
            :class="peelRight ? 'opacity-100' : 'opacity-0'"
          >
            <CvSectionExperience/>
          </div>
        </div>
      </div>
      <div 
        class="w-[33vw] h-full p-4 pt-0"
      >
        <div 
          ref="rightCont"
          class="w-full h-[95%] overflow-scroll"
          @scroll="handleLineUpScroll()"
        >
          <Icon
              v-if="showArrow"
              name="ic:round-keyboard-arrow-down" 
              class="text-[#22313f] absolute bottom-[5%] right-1 text-5xl"
          />
          <CvSectionEducation/> 
          <CvSectionSkills/>
        </div>
        <CvSectionContactMe
          class="flex-1 pt-2" 
        />
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
  const rightCont = ref()
  const showArrow = ref(true)
  
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

  function handleLineUpScroll() {
      const el = (rightCont.value) 
      const scrollTop = el.scrollTop
      const scrollHeight = el.scrollHeight
      const clientHeight = el.clientHeight

      if (scrollTop + clientHeight + 10 >= scrollHeight) {
          showArrow.value = false
      }
      else{
          showArrow.value = true
      }
  }
  
  onMounted(() => {
  })
  
  onBeforeUnmount(() => {
  })
  </script>
  