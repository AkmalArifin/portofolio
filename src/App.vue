<template>
  <main>
    <PageLoader/>
    <RouterView class="main-content"/>
  </main>
</template>

<script>
import PageLoader from "@/components/PageLoader.vue";

export default {
  name: "App",

  components: {
    PageLoader
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

</style>