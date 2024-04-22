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
        z-index: 10;
        display: inline;

        animation-name: load;
        animation-duration: 1s;
        animation-timing-function: ease-out;
        animation-play-state: paused;
        animation-fill-mode: forwards;
    }

    @keyframes load {
        0% {
            top: 0px;
        }
        70% {
            top: 0px;
        }
        100% {
            top: 100vh;
            display: none;
        }
    }
    
</style>