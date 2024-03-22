<template>
    <hr>
    <div class="project-wrapper">
        <div class="project-image">
            <div class="image">
                <img :src="image"/>
            </div>
        </div>
        <div class="project-details">
            <div class="text">
                <h1>{{ title }}<span style="color: var(--vt-c-orange-1)">.</span></h1>
                <br><br>
                <p>{{ paragraph }}</p>
                <br><br><br><br>
                <a :href="link" target="_blank"><button class="btn" type="button" >More</button></a>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "ListProject",
    props: [
        'image',
        'title',
        'paragraph',
        'link',
        'image',
    ]
}
</script>

<style scoped>

.project-wrapper {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    margin: 125px 0;
}

.project-image .image {
    display: flex;
    justify-content: center;
    align-items: center;
}

.project-image .image img {
    width: 150px;
}

.project-details {
    padding: 0px 32px;
    max-width: 70%;
}

h1 {
    font-family: 'PT Serif';
    font-weight: 700;
    font-size: 42px;
}

p {
    font-family: 'Hind Siliguri';
    font-size: 18px;
    line-height: 1.2;
}

.btn {
    font-family: 'raleway';
    font-size: 18px;
    font-style: italic;
    background-color: var(--vt-c-white-mute);
    border: 3px solid var(--vt-c-blue-1);
    border-radius: 10px;
    padding: 10px 50px;
    cursor: pointer;
}
.btn:hover {
    background-color: var(--vt-c-white-soft);
}

hr {
    border: 2px solid var(--vt-c-blue-1);
    border-radius: 2px;
}

@media (max-width: 800px) {
    .project-image {
        display: none;
    }
    .project-details {
        max-width: 100%;
    }
}
</style>