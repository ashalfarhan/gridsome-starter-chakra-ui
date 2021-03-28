<template>
  <Layout>
    <c-box w="container" mx="auto" mt="24">
      <!-- Learn how to use images here: https://gridsome.org/docs/images -->
      <c-flex
        :w="imageContainer"
        :direction="imageFlex"
        :h="imageContainerHeight"
        mx="auto"
        align="center"
        justify="space-between"
      >
        <g-image
          alt="Example image"
          src="~/assets/images/favicon.png"
          width="135"
        />
        <!-- Chakra provide image component as well, learn more here: 
          https://vue.chakra-ui.com/image -->

        <c-image :src="chakraIcon" w="250px" />
      </c-flex>
      <c-box text-align="center" my="8">
        <c-heading>Hello, world!</c-heading>
        <c-text>
          Welcome to Gridsome Starter Chakra-UI
        </c-text>
        <c-link href="https://gridsome.org/docs/" target="_blank" rel="noopener"
          >Gridsome Docs</c-link
        >
        <c-link
          ml="4"
          href="https://vue.chakra-ui.com/getting-started"
          target="_blank"
          rel="noopener"
          >Chakra-UI Docs</c-link
        >
      </c-box>
    </c-box>
  </Layout>
</template>

<script>
import ChakraIcon from "@/assets/svg/logo-colored.svg";
import ChakraIconDark from "@/assets/svg/logo-black.svg";
import {
  CBox,
  CImage,
  CFlex,
  CHeading,
  CText,
  CButton,
  CLink,
} from "@chakra-ui/vue";
export default {
  inject: ["$chakraColorMode"],
  components: {
    CBox,
    CFlex,
    CText,
    CImage,
    CLink,
    CButton,
    CHeading,
  },
  data() {
    return {
      ChakraIcon,
      ChakraIconDark,
      imageFlex: ["column", "column", "row", "row"],
      imageContainer: ["sm", "md"],
      imageContainerHeight: {
        sm: "240px",
        base: "240px",
        md: "auto",
      },
    };
  },
  computed: {
    colorMode() {
      return this.$chakraColorMode();
    },
    chakraIcon() {
      return this.colorMode === "light" ? this.ChakraIconDark : this.ChakraIcon;
    },
  },
  metaInfo() {
    return {
      title: "Hello, world!",
    };
  },
};
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
