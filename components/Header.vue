<template>
<div>
  <div class="flex justify-between font-serif border-b px-12 py-2">
    <div class="flex items-center uppercase text-xs">
      <div class="mr-4 font-display">
          Home
        </div>
        <div class="mr-4 font-display">
          About
        </div>
        <div class="mr-4 font-display">
          Writings
        </div>
        <div class="mr-4 font-display">
          Extras
        </div>
      </div>
      <div class="flex">
        <div><SocialIcon url="https://linkedin.com"/></div>
        <div><SocialIcon url="https://twitter.com/thebluefowl"/></div>
        <div><SocialIcon url="https://github.com"/></div>
      </div>
  
    
  </div>
  <div v-if="showPrimaryTitle" class="font-display font-extrabold text-8xl p-12 border-b">
      Vishnu <br> Jayadevan
    </div>
</div>
  
</template>

<script>
import SocialIcon from "./SocialIcon.vue"
export default {
  props: ["showPrimaryTitle"],
  name: 'Header',
  components: {SocialIcon}
}
</script>
