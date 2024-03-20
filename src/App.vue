<template>
  <main>
    <RouterView class="main-content"/>
  </main>
</template>

<style scoped>

.main-content {
  margin: 0 60px 100px;
}

@media (min-width: 512px) {
  .main-content {
    margin: 0 20px 60px;
  }
}

</style>