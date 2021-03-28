<template>
  <c-box max-w="100vw" min-height="100vh" v-bind="mainStyles[colorMode]">
    <app-header
      :site-name="siteName"
      :color-mode="colorMode"
      :toggle-color-mode="toggleColorMode"
    />
    <slot />
  </c-box>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import AppHeader from "@/components/Header.vue";
import { CBox } from "@chakra-ui/vue";

export default {
  name: "DefaultLayout",
  inject: ["$chakraColorMode", "$toggleColorMode"],
  components: {
    AppHeader,
    CBox,
  },
  computed: {
    siteName() {
      return this.$static.metadata.siteName;
    },
    colorMode() {
      return this.$chakraColorMode();
    },
    toggleColorMode() {
      return this.$toggleColorMode;
    },
    theme() {
      return this.$chakraTheme();
    },
  },
  data() {
    return {
      mainStyles: {
        dark: {
          bg: "gray.700",
          color: "whiteAlpha.900",
        },
        light: {
          bg: "white",
          color: "gray.900",
        },
      },
    };
  },
};
</script>
