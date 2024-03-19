<template>
    <div>
        <div class="landing-page">
            <div class="text">
                <h1>Hi, my<br>name is <span style="font-weight: 700;">Akmal</span><span style="color:var(--vt-c-orange-1)">.</span></h1>
                <br><br>
                <p>I'm an <span style="font-weight:700; color:var(--vt-c-blue-1)">undergraduate CS student</span> diving deep into the world of computing.</p>
            </div>
            <div class="photo">
                <img src="/public/photo-profile.jpg"/>
            </div>
        </div>
        <div class="about">
            <div class="text">
                <h1>Nice to meet you<span style="color: var(--vt-c-orange-1);">.</span></h1>
                <br><br>
                <hr>
                <br><br>
                <p>As an Institut Teknologi Bandung CS student, I'm driven by an insatiable curiosity about the potential of computing. From computer systems to web development. I eager to learn more about code in future - <span style="font-weight: 600;">the more, the merrier</span>.</p>
            </div>
        </div>
        <div class="projects">
            <div class="opening">
                <h1>My Projects<span style="color: var(--vt-c-orange-1)">.</span></h1>
                <br><br>
                <p>I'm passionate about applying my programming knowledge to solve real-world problems. To showcase this, I've undertaken several personal projects that you can see below.</p>
            </div>
            <br><br><br>
            <br><br><br>
            <br><br><br>    
            <ListProject 
                v-for="project in projects"
                :key="project.id"
                :title="project.title"
                :paragraph="project.paragraph"
                :link="project.link"
                :image="project.image"
            />
        </div>
        <!-- <div class="footer">
            <div class="text">
                <p>Learn More...</p> 
                <i class="fa fa-github" style="font-size:24px"></i>
            </div>
        </div> -->
    </div>
</template>

<script>
import { ref } from 'vue'
import ListProject from "@/components/ListProject.vue";

export default {
    name: "LandingPage",

    components: {
        ListProject
    },
    setup() {
        const projects = ref([
            { 
                id: 1, 
                title: 'Femu', 
                paragraph:'I had the opportunity to collaborate with a professor at Virginia Tech, USA, on contributions to the open-source FEMU project, a fast, accurate, scalable, and extensible NVMe SSD Emulator. My work focused on implementing a configuration interface for blackbox mode, specifically configure latency, SSD architecture and garbage collection threshold. This contribution was thoroughly tested to ensure proper configuration.',
                link: "https://github.com/vtess/FEMU",
                image: "public/ssd.png",
            },
            { 
                id: 2, 
                title: 'Autoscript Plot', 
                paragraph:"In my role as a dormitory advisor, I'm responsible for generating monthly reports on resident performance. To ensure accurate and efficient reporting, I've developed an automated script that compiles resident statistics. This approach allows me to provide a data-driven overview of resident activity and well-being.",
                link: "https://github.com/AkmalArifin/statistik-amalan-yaumi",
                image: "public/statistic.png",
            },
            {
                id: 3, 
                title: 'Rama', 
                paragraph:"As part of my undergraduate coursework, I worked on a project to develop a website for an external race management project, RAMA. In this project, I'm leveraging my design and front-end development skills to contribute to the user experience and functionality of the website.",
                link: "https://gitlab.informatika.org/ilhampratama2109/if3250_2023_k01_11_pro-04",
                image: "public/run.png",
            }
        ])
        return {
            projects
        }
    }

}
</script>

<style scoped>

.landing-page {
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 40px;
    padding: 0 2rem;

    min-height: 100vh;
}

.landing-page .text {
    grid-column: 1 / span 1;
    margin: auto;
}

.landing-page .photo {
    grid-column: 2 / span 1;
}

.landing-page h1 {
    font-family: 'PT Serif';
    font-size: 64px;
}

.landing-page p {
    font-family: 'raleway';
    font-size: 28px;
    font-style: italic;
}

.landing-page .photo {
    display: flex;
    justify-content: center;
    align-items: center;
}

.photo img {
    border-radius: 50%;
}

.about {
    padding: 100px 32px;
}

.about .text {
    max-width: 550px;
}

.about .text h1 {
    font-family: 'PT Serif';
    font-weight: 700;
    font-size: 48px;
}

.about .text hr {
    width: 17%;
    border: 2px solid var(--vt-c-blue-1);
    border-radius: 2px;
}

.about .text p {
    font-family: 'Hind Siliguri';
    font-size: 22px;
    line-height: 1.2;
}

.projects {
    padding: 100px 32px;
}

.projects .opening {
    max-width: 550px;
}

.projects .opening h1 {
    font-family: 'PT Serif';
    font-weight: 700;
    font-size: 42px;
}

.projects .opening p {
    font-family: 'Hind Siliguri';
    font-size: 22px;
    line-height: 1.2;
}

.projects hr {
    width: 100%;
    border: 2px solid var(--vt-c-blue-1);
    border-radius: 2px;
}

.footer {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--vt-c-blue-4);
    height: 250px;
}

.footer .text {
    font-family: 'raleway';
    text-align: center;
}
</style>

