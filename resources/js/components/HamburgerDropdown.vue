<template>
  <div v-click-outside="hide" class="relative block">
    <div>
      <span class="block flex justify-center">
        <button id="options-menu" type="button" class="flex border-none text-gray-800  focus:outline-none focus:shadow-outline-none  transition ease-in-out duration-150" aria-haspopup="true" aria-expanded="true" @click="toggle">
          <slot />
          <!-- Heroicon name: chevron-down -->
          <fa :icon="['fas', 'chevron-down']" class="my-auto mr-0 text-xs transition-all duration-300 ease-in-out svg-font font-12 sm:font-24" :class="isOpen ? 'flip-y' : ''" />
        </button>
      </span>
    </div>

    <transition
      enter-active-class="transition ease-out duration-100 transform"
      enter-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="transition ease-in duration-75 transform"
      leave-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <div v-show="isOpen" class="origin-top-right right-0 mt-2">
        <div class="p-2 " role="menu" aria-orientation="vertical" aria-labelledby="options-menu" @click="hide">
          <slot name="items" />
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import ClickOutside from 'vue-click-outside'

export default {
  name: 'HamburgerDropdown',
  directives: {
    ClickOutside
  },
  data: () => ({
    isOpen: false
  }),
  methods: {
    toggle: function () {
      this.isOpen = !this.isOpen
    },
    hide: function () {
      this.isOpen = false
    }
  }
}
</script>

<style scoped>
  .flip-y {
    transform: rotateX(180deg);
    transform-style: preserve-3d;
    margin-right: 0 !important;
  }
</style>
