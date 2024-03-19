<template>
    <div>
        <button class="btn" type="button">{{ text }}</button>
    </div> 
</template>

<script>
    export default {
        name: "Button",
        props: {
            text: String,
            link: String
        }
    }
</script>

<style scoped>

</style>