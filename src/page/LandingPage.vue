<template>
    <div>
        <section class="hello">
            <img class="blue-landing" src="/blue-landing.png" />
            <img class="yellow-landing" src="/yellow-landing.png" /> 
            <div class="hello-content">
                <div class="photo">
                    <img src="/photo-profile.jpg"/>
                </div>
                <div class="text">
                    <h1>Hi, my<br>name is <span style="font-weight: 700;">Akmal</span><span style="color:var(--vt-c-orange-1)">.</span></h1>
                    <br><br>
                    <p>I'm an <span style="font-weight:700; color:var(--vt-c-blue-1)">undergraduate CS student</span> diving deep into the world of computing.</p>
                </div>
            </div>
        </section>

        <section class="about">
            <img class="yellow-about" src="/yellow-line.png" />
            <img class="blue-about" src="/blue-circle.png" />
            <div class="about-content">
                <div class="text">
                    <h1>Nice to meet you<span style="color: var(--vt-c-orange-1);">.</span></h1>
                    <br><br>
                    <hr>
                    <br><br>
                    <p>As an Institut Teknologi Bandung CS student, I'm driven by an insatiable curiosity about the potential of computing. From computer systems to web development. I eager to learn more about code in future - <span style="font-weight: 600;">the more, the merrier</span>.</p>
                </div>
            </div>
        </section>

        <section class="projects">
            
            <div class="opening">
                <img class="blue-box" src="/blue-box.png" />
                <div class="opening-content">
                    <h1>My Projects<span style="color: var(--vt-c-orange-1)">.</span></h1>
                    <br><br>
                    <p>I'm passionate about applying my programming knowledge to solve real-world problems. To showcase this, I've undertaken several personal projects that you can see below.</p>
                </div>
            </div>

            <br><br><br>
            <br><br><br>
            <br><br><br>

            <div class="projects-list">
                <ListProject 
                    v-for="project in projects"
                    :key="project.id"
                    :title="project.title"
                    :paragraph="project.paragraph"
                    :link="project.link"
                    :image="project.image"
                />
            </div>
        </section>

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
                paragraph:`Low-level programming has always been intimidating for me. Fortunately, I recently had the opportunity to work on an open-source project that required low-level work.The project is FEMU, a fast, accurate, scalable, and extensible NVMe SSD Emulator. I contributed by implementing a configuration interface for blackbox mode.`,
                link: "https://github.com/vtess/FEMU",
                image: "./ssd-graphics.png",
            },
            { 
                id: 2, 
                title: 'Autoscript Plot', 
                paragraph:"In my role as a dormitory advisor, I'm responsible for generating monthly reports on resident performance. To ensure accurate and efficient reporting, I've developed an automated script that compiles resident statistics. This approach allows me to provide a data-driven overview of resident activity and well-being.",
                link: "https://github.com/AkmalArifin/statistik-amalan-yaumi",
                image: "./statistic-graphics.png",
            },
            {
                id: 3, 
                title: 'Rama', 
                paragraph:"As part of my undergraduate coursework, I worked on a project to develop a website for an external race management project, RAMA. In this project, I'm leveraging my design and front-end development skills to contribute to the user experience and functionality of the website.",
                link: "https://gitlab.informatika.org/ilhampratama2109/if3250_2023_k01_11_pro-04",
                image: "./run-graphics.png",
            }
        ])
        return {
            projects
        }
    }

}
</script>

<style scoped>


.hello {
    position: relative;
    min-height: 100vh;
}

.blue-landing {
    position: absolute;
    width: 600px;
    left: calc(-60px - 20px);
    bottom: 0px;
    z-index: -1;
}

.yellow-landing {
    position: absolute;
    width: 600px;
    right: -100px;
    top: -20px;
    z-index: -1;
}

.hello-content {
    display: flex;
    flex-direction: row;
    gap: minmax(20px, auto);
    align-items: center;
    justify-content: space-evenly;
    height: calc(100vh - 40px)
}

.hello-content .text {
    width: 550px;
    order: 2;
}

.hello-content .text h1 {
    font-family: 'PT Serif';
    font-size: 64px;
}

.hello-content .text p {
    font-family: 'raleway';
    font-size: 28px;
    font-style: italic;
}

.hello-content .photo {
    display: flex;
    justify-content: center;
    align-items: center;
    order: 1;
}

.photo img {
    border-radius: 50%;
}

.about {
    position: relative;
    margin: 250px auto;
    max-width: 80%;
    display: flex;
    justify-content: space-between;
}

.yellow-about {
    position: absolute;
    width: 300px;
    right: 50px;
    top: 35px;
    rotate: 15deg;
    z-index: -1;
}

.blue-about {
    position: absolute;
    width: 220px;
    right: -70px;
    rotate: -5deg;
    z-index: -1;
}

.about-content {
    order: 1;
    width: 50%;
}
.about-graphics {
    order: 2;
    width: 50%;
}

.about-content .text h1 {
    font-family: 'PT Serif';
    font-weight: 700;
    font-size: 48px;
}

.about-content .text hr {
    width: 17%;
    border: 2px solid var(--vt-c-blue-1);
    border-radius: 2px;
}

.about-content .text p {
    font-family: 'Hind Siliguri';
    font-size: 18px;
    line-height: 1.5;
}

.projects {
    margin: 250px auto;
    max-width: 80%;
}

.opening {
    position: relative;
    display: flex;
    justify-content: flex-end;
}

.blue-box {
    position: absolute;
    width: 350px;
    left: -20px;
    top: -30px;
    transform: scaleX(-1);
}

.opening-content {
    order: 1;
    width: 50%;
}

.opening-content h1 {
    font-family: 'PT Serif';
    font-weight: 700;
    font-size: 42px;
    text-align: right;
}

.opening-content p {
    font-family: 'Hind Siliguri';
    font-size: 18px;
    line-height: 1.5;
    text-align: right;
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

@media (max-width: 1024px) {
    
    .blue-landing {
        display: none;
    }

    .yellow-landing {
        display: none;
    }

    .blue-about {
        display: none;
    }

    .yellow-about {
        display: none;
    }

    .hello-content {
        position: relative;
        display: block;
    }

    .hello-content .text {
        text-align: center;
        margin-top: 40px;
        width: calc(100vw - 160px);
    }
    
    .about {
        margin: 100px auto;
    }

    .about-content {
        width: 100%;
    }

    .about-graphics {
        display: none;
    }

    .projects {
        margin: 100px auto;
    }

    .opening-content {
        width: 100%;
    }

    .opening-graphics {
        display: none;
    }
} 

@media (max-width: 800px) {
    .about {
        max-width: 100%;
    }

    .projects {
        max-width: 100%;
    }
}

@media (max-width: 512px) {
    .hello-content .photo img {
        width: 250px;
    }

    .hello-content .text {
        margin-top: 10px;
        width: calc(100vw - 80px);
    }
    
    .hello-content .text h1 {
        font-size: 48px;
    }

    .about {
        margin: 50px 25px;
    }

    .projects {
        margin: 50px 25px;
    }
}

</style>

