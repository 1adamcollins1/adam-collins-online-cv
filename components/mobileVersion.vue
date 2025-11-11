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
        <div class="absolute z-30 h-full w-full flex flex-col-reverse">
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[33] flex flex-col"
            :class="activeSection === 'education' ? 'h-[72%]' : 'h-[8%]'"
          >
            <div class="pl-10 box-border border-b-4">
              <h2
                class="relative w-fit bg-[#8dc6ff] px-3 text-3xl rounded-t-sm font-bold border-4 border-b-[#8dc6ff] box-border translate-y-[4px]"
                @click="activeSection === 'education' ? activeSection= '' : activeSection= 'education'"
              >
                Education
              </h2>
            </div>
            <CvSectionEducation
              hide-header
              class="flex-1 bg-[#8dc6ff] transition-opacity duration-500 text-black text-[15px] p-4"
            />
          </div>
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[32] flex flex-col"
            :class="activeSection === 'experience' ? 'h-[72%]' : 'h-[8%]'"
          >
            <div class="pl-6 box-border border-b-4">
              <h2
                class="relative w-fit bg-[#8dc6ff] px-3 text-3xl rounded-t-sm font-bold border-4 border-b-[#8dc6ff] box-border translate-y-[4px]"
                @click="activeSection === 'experience' ? activeSection= '' : activeSection= 'experience'"
              >
                Experience
              </h2>
            </div>

            <div class=" bg-[#8dc6ff] transition-opacity duration-500 text-black text-[15px] p-4">
              <CvSectionExperience
                hide-header
              />
            </div>
          </div>
          <div 
            class="relative text-[#e4f1fe] transition-[height] duration-500 z-[31] flex flex-col"
            :class="activeSection === 'skills' ? 'h-[72%]' : 'h-[8%]'"
          >
            <div class="pl-2 box-border border-b-4">
              <h2
                class="relative w-fit bg-[#8dc6ff] px-3 text-3xl rounded-t-sm font-bold border-4 border-b-[#8dc6ff] box-border translate-y-[4px]"
                @click="activeSection === 'skills' ? activeSection= '' : activeSection= 'skills'"
              >
                Skills
              </h2>
            </div>
            <CvSectionSkills
              hide-header
              class="flex-1 bg-[#8dc6ff] transition-opacity duration-500 text-black text-[15px] p-4"
            />
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

const pinTitle = ref(true)
const pinTitleChildren = ref(true)
const pinTitleChildrenTwo = ref(true)
const activeSection = ref('')

function toggleTitle() {
  pinTitle.value = true
  setTimeout(() => pinTitleChildren.value = true, 300)
  setTimeout(() => pinTitleChildrenTwo.value = true, 600)
}

onMounted(() => {
})

onBeforeUnmount(() => {
})
</script>
