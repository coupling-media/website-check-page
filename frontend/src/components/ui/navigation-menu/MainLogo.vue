<script setup lang="ts">
import { computed } from "vue";
import { useColorMode } from "@vueuse/core";

const mode = useColorMode();

const logoSrc = computed(() => {
  return mode.value === "dark"
      ? "/coupling-logo-light.svg"
      : "/coupling-logo-dark.svg";
});
</script>

<template>
  <a
      href="/"
      class="flex items-center gap-2 select-none"
  >
    <img
        :src="logoSrc"
        alt="Logo"
        class="h-10 w-auto transition-opacity duration-300 p-1 ml-1"
    />
  </a>
</template>


