<template>
  <div>
    <span
      class="absolute text-white text-4xl top-5 left-4 cursor-pointer"
      @click="toggleSidebar"
    >
      <i class="bi bi-filter-left px-2 bg-gray-900 rounded-md"></i>
    </span>
    <div
      :class="{ hidden: !isOpen }"
      class="sidebar fixed top-0 bottom-0 lg:left-0 p-2 w-[300px] overflow-y-auto text-center bg-sonic-primary"
    >
      <div
        class="p-2.5 mt-3 flex items-center rounded-md px-4 duration-300 cursor-pointer hover:bg-blue-600 text-white"
      >
        <i class="bi bi-house-door-fill"></i>
        <span class="text-[15px] ml-4 text-gray-200 font-bold">Home</span>
      </div>
      <div
        class="p-2.5 mt-3 flex items-center rounded-md px-4 duration-300 cursor-pointer hover:bg-blue-600 text-white"
      >
        <i class="bi bi-box-arrow-in-right"></i>
        <span class="text-[15px] ml-4 text-gray-200 font-bold">User</span>
      </div>
    </div>
    <button
      v-if="isOpen"
      @click="toggleSidebar"
      class="fixed top-5 right-5 text-white text-lg bg-gray-900 rounded-full w-10 h-10 flex items-center justify-center"
    >
      <i class="bi bi-x"></i>
    </button>
  </div>
</template>
  
  <script>
export default {
  name: "Sidebar",
  data() {
    return {
      isOpen: true,
      isSidebarOpen: false,
      currentSidebarTab: null,
      isSettingsPanelOpen: false,
      isSubHeaderOpen: false,
      watchScreen() {
        if (window.innerWidth <= 1024) {
          this.isSidebarOpen = false;
        }
      },
    };
  },
  methods: {
    toggleSidebar() {
      this.isOpen = !this.isOpen;
    },
    setup() {
      return {
        isSidebarOpen: false,
        currentSidebarTab: null,
        isSettingsPanelOpen: false,
        isSubHeaderOpen: false,
        watchScreen() {
          if (window.innerWidth <= 1024) {
            this.isSidebarOpen = false;
          }
        },
      };
    },
  },
};
</script>
  
  <style>
/* Add your component-specific styles here */
</style>
  