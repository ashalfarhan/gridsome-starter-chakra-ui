<template>
  <c-theme-provider>
    <c-color-mode-provider>
      <c-box font-family="body" as="main">
        <c-reset />
        <router-view />
      </c-box>
    </c-color-mode-provider>
  </c-theme-provider>
</template>

<script>
import {
  CColorModeProvider,
  CThemeProvider,
  CReset,
  CBox,
} from "@chakra-ui/vue";
export default {
  name: "App",
  components: {
    CColorModeProvider,
    CThemeProvider,
    CReset,
    CBox,
  },
};
</script>
