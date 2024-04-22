<template>
    <div class="loader">
        
    </div>
</template>
<script>
export default {
    name: "PageLoader"
}
</script>
<style>
    .loader {
        position: fixed;
        background: #98D0FF url(/preloader.gif) no-repeat center center;
        background-size: 4%;
        height: 100vh;
        width: 100%;
        z-index: 10;
    }
</style>