<template>
  <main>
    <Frame class="frame"/>
    <PageLoader/>
    <RouterView class="main-content"/>
  </main>
</template>

<script>
import PageLoader from "@/components/PageLoader.vue";
import Frame from "@/components/Frame.vue";

export default {
  name: "App",

  components: {
    PageLoader,
    Frame
  },
}
</script>

<script>

</script>

<style scoped>

.main-content {
  margin: 0 20px 60px;
}

@media (min-width: 512px) {
  .main-content {
    margin: 0 60px 100px;
  }
}

@media (max-width: 1024px) {
  .frame {
    display: none;
  }
}

</style>