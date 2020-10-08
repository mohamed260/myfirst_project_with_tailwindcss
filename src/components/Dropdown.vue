<template>
        <div class=" relative">
            <button @click="toggle" class="block focus:outline-none" @focus="buttonFocus = true" @blur="buttonFocus = false">
              <slot name="triger" :hasFocused="buttonHasFocus" :isOpen="isOpen"></slot>
            </button>
            <div :class="isOpen ? 'sm:block' : 'sm:hidden'">
              <button @click="isOpen = false" class="z-30 block fixed inset-0 w-full h-full cursor-default"></button>
              <div class="absolute z-40 right-0">
                <slot name="dropdown"></slot>
              </div>
            </div>
        </div>
</template>



<script>
export default {
 props: [],
 data() {
     return {
         isOpen: false,
         buttonHasFocus: false,
     }
 },

 mounted() {
     const onEscape = (e) => {
      if (!this.isOpen || e.key !== 'Escape') {
        return 
      }
      console.log('closing')
      this.isOpen = false
   }
   document.addEventListener('keydown', onEscape)

   this.$on('hook:destroyed', () => {
     document.removeEventListener('keydown', onEscape)
   })
 },

 methods: {

     toggle() {
         this.isOpen = !this.isOpen;
     }

 },
}
</script>

<style>

</style>