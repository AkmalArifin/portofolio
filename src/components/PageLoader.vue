<template>
    <div ref="preloader" class="preloader">
    </div>
</template>

<script setup>
import { ref } from 'vue';

const preloader = ref(null);

window.addEventListener("load", function() {
    console.log(preloader.value);

    preloader.value.style.animationPlayState = "running";
});

</script>

<script>
export default {
    name: "PageLoader",
}
</script>

<style>
    .preloader {
        position: fixed;
        background: #98D0FF url(/preloader.gif) no-repeat center center;
        background-size: 4%;
        height: 100vh;
        width: 100%;
        z-index: 2;
        display: inline;

        animation: load .5s cubic-bezier(0.22, 0.61, 0.36, 1) .25s forwards;
        animation-delay: 1s;
        animation-play-state: paused;
    }
</style>