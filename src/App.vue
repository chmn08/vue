<template>
  <div class="flex flex-col min-h-screen font-Roboto bg-gray-200">
    <template v-if="!isLoginPage">
      <Sidebar />
      <RouterView class="flex-1" v-slot="{ Component }">
        <Transition name="page">
          <component :is="Component" />
        </Transition>
      </RouterView>
    </template>
    <template v-else>
      <RouterView class="flex-1" v-slot="{ Component }">
        <Transition name="page">
          <component :is="Component" />
        </Transition>
      </RouterView>
    </template>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed } from "vue";
import Sidebar from "./components/sidebar.vue";
import { useRoute } from "vue-router";

export default defineComponent({
  components: {
    Sidebar,
  },
  setup() {
    const route = useRoute();
    const isLoginPage = computed(() => route.name === "login");

    return {
      isLoginPage,
    };
  },
});
</script>
