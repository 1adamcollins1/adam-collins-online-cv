<template>
    <div class="flex flex-col flex-wrap gap-2 items-end">
        <!-- <p class="bg-[#22313f] text-[#e4f1fe] px-3 rounded-sm right-0 w-fit">adamcollins31@gmail.com</p> -->
        <div class="social-icons align-middle" style="display: flex; gap: 8px; flex-wrap: wrap; justify-content: center;">
            <p 
                class="hidden lg:block lg:text-2xl pb-0 h-fit"
                v-if="!hideHeader"
            >
                Contact me:
            </p>
            <a href="https://www.linkedin.com/in/adam-collins-b32196125/" target="_blank" rel="noopener" style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; padding: 8px; background: rgba(34, 49, 63, 1); border-radius: 8px; color: #e4f1fe; text-decoration: none;" >
                <svg class="niftybutton-linkedin" data-donate="true" data-tag="lin" data-name="LinkedIn" viewBox="0 0 512 512" preserveAspectRatio="xMidYMid meet" width="40px" height="40px" style="width: 40px; height: 40px; display: block; fill: #e4f1fe;"><title>LinkedIn social icon</title>
                    <path d="M186.4 142.4c0 19-15.3 34.5-34.2 34.5 -18.9 0-34.2-15.4-34.2-34.5 0-19 15.3-34.5 34.2-34.5C171.1 107.9 186.4 123.4 186.4 142.4zM181.4 201.3h-57.8V388.1h57.8V201.3zM273.8 201.3h-55.4V388.1h55.4c0 0 0-69.3 0-98 0-26.3 12.1-41.9 35.2-41.9 21.3 0 31.5 15 31.5 41.9 0 26.9 0 98 0 98h57.5c0 0 0-68.2 0-118.3 0-50-28.3-74.2-68-74.2 -39.6 0-56.3 30.9-56.3 30.9v-25.2H273.8z" fill="#e4f1fe"></path>
                </svg>
            </a>
            <div class="tooltip-container">
                <a 
                href="#"
                @click.prevent="copyOnClick('email')"
                @mouseenter="copyEmailText = 'Click to copy email'"
                class="copy-btn"
                >
                <svg class="niftybutton-email" viewBox="0 0 512 512" preserveAspectRatio="xMidYMid meet" width="40px" height="40px" style="width: 40px; height: 40px; display: block; fill: #e4f1fe;">
                    <path d="M101.3 141.6v228.9h0.3 308.4 0.8V141.6H101.3zM375.7 167.8l-119.7 91.5 -119.6-91.5H375.7zM127.6 194.1l64.1 49.1 -64.1 64.1V194.1zM127.8 344.2l84.9-84.9 43.2 33.1 43-32.9 84.7 84.7L127.8 344.2 127.8 344.2zM384.4 307.8l-64.4-64.4 64.4-49.3V307.8z"></path>
                </svg>
                </a>
                <span class="tooltip-text">{{ copyEmailText }}</span>
            </div>
            <div class="tooltip-container">
                <a 
                href="#"
                @click.prevent="copyOnClick('phone')"
                @mouseenter="copyPhoneText = 'Click to copy phone number'"
                class="copy-btn"
                >
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" stroke-width="1.5" class="niftybutton-phone" preserveAspectRatio="xMidYMid meet" width="40px" height="40px" style="width: 40px; height: 40px; display: block; fill: #e4f1fe;">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z" fill="#e4f1fe"></path>
                </svg>
                </a>
                <span class="tooltip-text">{{ copyPhoneText }}</span>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
    interface Props {
        hideHeader?: boolean
    }

    defineProps<Props>()

    const copyEmailText = ref('Click to copy email')
    const copyPhoneText = ref('Click to copy phone number')

    function copyOnClick(copyType: string) {
        const toCopy = (copyType == 'email') ? 'adamcollins31@gmail.com' : '+44 7592738027'
        navigator.clipboard.writeText(toCopy)
            .then(() => {
                (copyType == 'email') ? copyEmailText.value = 'Copied!' : copyPhoneText.value = 'Copied!'
            })
            .catch(err => {
            console.error("Failed to copy email: ", err);
            });
    }
</script>

<style scoped>
.tooltip-container {
  position: relative;
  display: inline-block;

align-items: center;
}

.copy-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  padding: 8px;
  background: rgba(34, 49, 63, 1);
  border-radius: 8px;
  color: #e4f1fe;
  text-decoration: none;
}

/* Tooltip styling */
.tooltip-text {
  visibility: hidden;
  width: max-content;
  background-color: rgba(0,0,0,0.8);
  color: #fff;
  text-align: center;
  border-radius: 4px;
  padding: 4px 8px;
  position: absolute;
  z-index: 10;
  bottom: 125%; /* above the icon */
  left: 100%;
  transform: translateX(-100%);
  opacity: 0;
  transition: opacity 0.1s ease; /* instant-ish */
  pointer-events: none;
  font-size: 12px;
}

/* Show tooltip immediately on hover */
.tooltip-container:hover .tooltip-text {
  visibility: visible;
  opacity: 1;
}
</style>