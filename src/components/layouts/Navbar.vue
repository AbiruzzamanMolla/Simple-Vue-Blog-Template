<template>
    <nav id="navbar"
    class="px-4 py-4 sm:py-6 bg-white shadow sm:bg-gray-900 sm:shadow-none sm:fixed w-full z-10">
      <div class="container mx-auto flex flex-col sm:flex-row items-center justify-between">
        <div class="w-full flex flex-row items-center justify-between">
          <div class="text-3xl font-bold">
            <span class="sm:text-white">Abir's</span>
            <span class="text-primary">Project</span>
          </div>
          <div>
            <button v-show="!isVisible" class="sm:hidden" @click="toggle">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            </button>
            <button v-show="isVisible" class="sm:hidden" @click="toggle">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
            </button>
          </div>
        </div>
        <div class="mt-4 sm:mt-0 w-full sm:space-x-4 sm:text-right sm:block sm:text-white" :class="{ 'hidden' : !isVisible }">
          <NavbarLinkVue to="/articles" label="Articles" />
          <NavbarLinkVue to="/about" label="About" />
          <NavbarLinkVue to="/contact" label="Contact" />
        </div>
      </div>
    </nav>
</template>

<script>
import NavbarLinkVue from "./NavbarLink.vue";
import { useToggle } from "@/composables/useToggle"
export default {
  components: {
    NavbarLinkVue
  },
  props: {},
  setup() {
    let { isVisible, toggle } = useToggle();

    return {
      isVisible,
      toggle,
    }
  },
};
</script>