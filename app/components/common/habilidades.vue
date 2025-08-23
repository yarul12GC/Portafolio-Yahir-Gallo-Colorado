<script setup lang="ts">
function getSkills() {
    return [
        { category: "Bases de Datos", items: ["MySQL", "PostgreSQL"] },
        { category: "Business Intelligence", items: ["Power BI (nivel básico)"] },
        { category: "Programación Back-End", items: ["PHP"] },
        { category: "Programación Front-End", items: ["JavaScript", "HTML, CSS, Bootstrap"] },
        { category: "Frameworks Front-End", items: ["Angular", "Astro", "Nuxt 3", "Vue 3"] },
        { category: "Desarrollo Web", items: ["Sitios responsivos", "Webs dinámicas"] },
        { category: "Administración de Hosting", items: ["cPanel", "Gestión de servidores y despliegues"] },
        { category: "Control de Versiones", items: ["Git", "GitHub", "SourceTree", "Bitbucket"] },
        { category: "Gestión de Proyectos", items: ["Jira", "Metodología Scrum"] }
    ]
}

function getTechnologies() {
    return [
        {
            name: "PHP",
            src: "php.svg",
        },
        {
            name: "NUXT 3",
            src: "descarga.png",
        },
        {
            name: "VUE 3",
            src: "Vue.js.svg",
        },
        {
            name: "ANGULAR",
            src: "angular.png",
        },
        {
            name: "SQL",
            src: "servidor-sql.png",
        },
        {
            name: "CSS",
            src: "css.png",
        },
        {
            name: "JavaScript",
            src: "JS.png",
        },
        {
            name: "HTML",
            src: "html.png",
        },
        {
            name: "BOOTSTRAP",
            src: "bootstrap-logo.svg",
        },
        {
            name: "WORDPRESS",
            src: "wordpress.png",
        },
        {
            name: "GIT",
            src: "git.png",
        },
        {
            name: "GITHUB",
            src: "github-logo.png",
        },
    ]
}

const skills = getSkills()
const technologies = getTechnologies()
</script>

<template>
    <section class="skills-section pt-3" id="skills">
        <div class="row g-4 mb-5">
            <div v-for="(skill, index) in skills" :key="index" class="col-12 col-md-6 col-lg-3">
                <div class="card skill-card h-100">
                    <div class="card-body">
                        <h5 class="text-info mb-3 color">{{ skill.category }}</h5>
                        <ul class="list-unstyled mt-2">
                            <li v-for="(item, idx) in skill.items" :key="idx" class="d-flex align-items-center mb-2">
                                <span class="dot me-2"></span> {{ item }}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <h3 class="mb-4 colorT">
            Tecnologías que manejo
        </h3>

        <div class="row g-4 justify-content-center">
            <div v-for="(tech, i) in technologies" :key="i" class="col-6 col-md-4 col-lg-2">
                <div class="card tech-card h-100 text-center">
                    <div class="card-body d-flex flex-column align-items-center justify-content-center p-4">
                        <div class="icon-wrapper mb-3">
                            <img :src="`/img/${tech.src}`" :alt="tech.name" class="tech-icon" loading="lazy" />
                        </div>
                        <p class="mb-0 text-light fw-semibold small">{{ tech.name }}</p>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>

<style scoped>
.skills-section {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
}

.card {
    border: none ! important;
    box-shadow: #cecece92 1.95px 1.95px 2.6px;

}

.skill-card {
    background-color: rgb(19 21 26);
    border: 1px solid #2c2c2c;
    border-radius: 15px;
    transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
}

.skill-card:hover {
    transform: translateY(-8px);
    border-color: #0dcaf0;
    box-shadow: #0dcaf0 1.95px 1.95px 2.6px;
}

.card-title {
    font-weight: 600;
    letter-spacing: 0.5px;
}

.dot {
    width: 8px;
    height: 8px;
    background: #0dcaf0;
    border-radius: 50%;
    display: inline-block;
    animation: pulse 2s infinite;
}

@keyframes pulse {

    0%,
    100% {
        transform: scale(1);
        opacity: 0.7;
    }

    50% {
        transform: scale(1.25);
        opacity: 1;
    }
}

.tech-card {
    background-color: rgb(19 21 26);
    border: 1px solid #2c2c2c;
    border-radius: 14px;
    transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
}

.tech-card:hover {
    transform: translateY(-8px) scale(1.02);
    border-color: #0dcaf0;
    box-shadow: #0dcaf0 1.95px 1.95px 2.6px;
}

.icon-wrapper {
    width: 86px;
    height: 86px;
    border-radius: 50%;
    background: radial-gradient(circle at 50% 50%, rgba(13, 202, 240, 0.22), rgba(13, 202, 240, 0.06));
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(2px);
    border: 1px solid rgba(13, 202, 240, 0.24);
}

.tech-icon {
    max-width: 60px;
    max-height: 60px;
    filter: drop-shadow(0 0 6px rgba(13, 202, 240, 0.45));
    transition: transform 0.35s ease;
}

.tech-card:hover .tech-icon {
    transform: rotate(6deg) scale(1.08);
}

@media (max-width: 575.98px) {
    .icon-wrapper {
        width: 76px;
        height: 76px;
    }

    .tech-icon {
        max-width: 52px;
        max-height: 52px;
    }
}
</style>
