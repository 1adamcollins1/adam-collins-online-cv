<template>
  <div 
    class="h-dvh w-screen relative flex flex-row transition-all duration-1000"
    :class="[
      loaded ? 'opacity-100' : 'opacity-0'
    ]"
  >
    <div class="relative h-full w-screen portrait:flex landscape:hidden">
      
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
          <CvSectionAboutMe
            @click="toggleTitle()"
            :pin-title="pinTitle"
            :pin-title-children="pinTitleChildren"
            class="h-[18%]"
          />
          <div class="h-[20%]"></div>
          <div 
            class="h-[60%] text-center flex justify-center items-center flex-col pb-12 px-4"
            :class="pinTitleChildren ? 'opacity-100' : 'opacity-0'"
          >
            <img src="../public/images/profilepic.png" alt="" class="w-32 h-44">
            <p class="text-[17px]">
              I am a personable Front-End Developer with over 5 years of experience building modern, scalable web and mobile applications. I have contributed to all stages of development from concept and testing to final delivery, providing value across the board. From B2B, agency work, start ups and more. 
            </p>
          </div>
        </div>
        <div class="absolute pointer-events-none z-30 h-full w-full flex flex-col-reverse">
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[33] pointer-events-auto"
            :class="activeSection === 'education' ? 'h-[70%]' : 'h-[7%]'"
          >
            <div class="pl-20 box-border">
              <h2
                class="relative w-fit bg-[#65adf5] px-3 text-2xl rounded-t-md font-bold box-border"
                @click="activeSection === 'education' ? activeSection= '' : activeSection= 'education'"
              >
                Education
              </h2>
            </div>
            <div class="h-dvh pb-[35dvh] overflow-scroll bg-[#65adf5] transition-opacity duration-500 text-black text-[17px] p-4">
              <CvSectionEducation
                hide-header
                class="transition-opacity duration-500"
                :class="activeSection === 'education' ? 'opacity-100' : 'opacity-0'"
              />
            </div>
          </div>
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[32] pointer-events-auto"
            :class="activeSection === 'experience' ? 'h-[65%]' : 'h-[5.5%]'"
          >
            <div class="pl-10 box-border">
              <h2
                class="relative w-fit bg-[#8dc6ff] px-3 text-2xl rounded-t-md font-bold box-border"
                @click="activeSection === 'experience' ? activeSection= '' : activeSection= 'experience'"
              >
                Experience
              </h2>
            </div>

            <div class="h-dvh pb-[40dvh] overflow-scroll bg-[#8dc6ff] transition-opacity duration-500 text-black text-[17px] p-4">
              <CvSectionExperience
                hide-header
                class="transition-opacity duration-500"
                :class="activeSection === 'experience' ? 'opacity-100' : 'opacity-0'"
              />
            </div>
          </div>
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[31] pointer-events-auto"
            :class="activeSection === 'skills' ? 'h-[55%]' : 'h-[5.5%]'"
          >
            <div class="pl-2 box-border">
              <h2
                class="relative w-fit bg-[#65adf5] px-3 text-2xl rounded-t-md font-bold box-border"
                @click="activeSection === 'skills' ? activeSection= '' : activeSection= 'skills'"
              >
                Skills
              </h2>
            </div>
            <div class="h-dvh pb-[50dvh] overflow-scroll bg-[#65adf5] transition-opacity duration-500 text-black text-[17px] p-4">
              <CvSectionSkills
                hide-header
                class="transition-opacity duration-500"
                :class="activeSection === 'skills' ? 'opacity-100' : 'opacity-0'"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="portrait:hidden landscape:flex w-full h-full text-center justify-center">
      <p class="text-[#e4f1fe] font-bold text-4xl h-fit m-auto">Please rotate your phone!</p>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount } from 'vue'

const hideOverlay = ref(false)

const pinTitle = ref(true)
const pinTitleChildren = ref(true)
const pinTitleChildrenTwo = ref(true)
const activeSection = ref('')
const loaded = ref(false)

function toggleTitle() {
  pinTitle.value = true
  setTimeout(() => pinTitleChildren.value = true, 300)
  setTimeout(() => pinTitleChildrenTwo.value = true, 600)
}

onMounted(() => {
  loaded.value = true
})

onBeforeUnmount(() => {
})
</script>
