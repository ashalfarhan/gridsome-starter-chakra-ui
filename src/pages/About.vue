<template>
  <Layout>
    <c-box w="container" mx="auto" mt="12">
      <c-heading>About us</c-heading>
      <c-text>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error
        doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur
        rerum illum odit fugit assumenda rem dolores inventore iste
        reprehenderit maxime! Iusto.
      </c-text>
    </c-box>
  </Layout>
</template>

<script>
import { CBox, CHeading, CText } from "@chakra-ui/vue";
export default {
  components: {
    CBox,
    CHeading,
    CText,
  },
  metaInfo: {
    title: "About us",
  },
};
</script>
