<template>
    <section class=" py-2" id="portafolio">

        <div class="row g-4">
            <div v-for="(proyecto, index) in proyectosp" :key="index" class="col-12 col-md-6 col-lg-4">
                <div class="card h-100  project-card">
                    <img :src="`/img/${proyecto.galeri}`" :alt="proyecto.proyecto" class="card-img-top"
                        v-if="proyecto.galeri !== ''" />

                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-semibold">{{ proyecto.proyecto }}</h5>

                        <p class="card-text text-muted small">
                            {{ proyecto.description }}
                        </p>

                        <div class="mt-2 mb-3">
                            <span v-for="(tech, tIndex) in proyecto.technologies" :key="tIndex"
                                class="badge bg-secondary me-1">
                                {{ tech }}
                            </span>
                        </div>

                        <div class="mt-auto d-flex justify-content-between"
                            v-if="proyecto.liveUrl !== '' && proyecto.repoUrl !== ''">
                            <a :href="proyecto.liveUrl" target="_blank" class="btn btn-sm btnProyecto">
                                Ver Proyecto
                            </a>
                            <a :href="proyecto.repoUrl" target="_blank" class="btn btn-sm btnProyecto">
                                Código
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
const proyectosp = [
    {
        proyecto: "SISTEMA DE PRACTICA PARA LA CAPTURA DE PEDIMENTOS",
        description:
            "Sistema de práctica para la capacitación en la captura de datos de pedimentos. Al finalizar, el sistema genera un PDF con códigos de barras y QR creados a partir de la información ingresada.",
        galeri: "pedimento.jpeg",
        liveUrl: "https://certicenca.cencacomex.com.mx/pedimento-/",
        repoUrl: "https://github.com/yarul12GC/pedimento-",
        technologies: ["PHP", "HTML", "CSS", "Bootstrap", "JavaScript", "MySQL"],
    },
    {
        proyecto: "SISTEMA INTEGRAL PARA LA GESTIÓN DE CERTIFICADOS Y DOCUEMTOS",
        description:
            "Sistema web que gestiona certificados, documentos y materiales de estudio otorgados durante cursos, diplomados o webinars en CENCA Comercio Exterior.",
        galeri: "image.png",
        liveUrl: "https://certicenca.cencacomex.com.mx/",
        repoUrl: "https://github.com/yarul12GC/certicenca",
        technologies: ["PHP", "MySQL", "Bootstrap", "CSS"],
    },
    {
        proyecto: "BIBLIOTECA ADUANERA",
        description:
            "Sistema que compila leyes, reglas y decretos de comercio exterior. Incluye una interfaz intuitiva para navegar entre artículos y facilitar la consulta rápida de información.",
        galeri: "bibliotecaadn.jpeg",
        liveUrl: "https://leyes.vercel.app/panel",
        repoUrl: "https://github.com/yarul12GC/leyes",
        technologies: ["Angular", "HTML", "CSS", "Bootstrap"],
    },

    {
        proyecto: "REESTRUCTURACIÓN DE LA PÁGINA PRINCIPAL",
        description:
            "Reestructuración de la página principal de la empresa en WordPress, mejorando su funcionalidad, diseño y experiencia de usuario.",
        galeri: "",
        liveUrl: "",
        repoUrl: "",
    },
    {
        proyecto: "INTERFAZ DE INSPECCION DE IMAGENES",
        description:
            "Desarrollé la interfaz de un sistema de inspección de imágenes para la empresa en la que actualmente trabajo, incorporando la generación de reportes por intervalos de fechas. Me enfoqué en el desarrollo frontend, consumiendo APIs y utilizando librerías en JavaScript con el framework Vue 3 y Nuxt 3. Es importante destacar que el sistema maneja diferentes rangos de usuarios y es utilizado por varias aseguradoras, cada una con un perfil personalizado acorde a sus colores institucionales. Además, el sistema funciona de manera dinámica gracias a la información obtenida desde las APIs.",
        galeri: "",
        liveUrl: "",
        repoUrl: "",
    },
    {
         proyecto: "NOTA:",
        description:
"Los proyectos presentados son una muestra de los trabajos realizados a lo largo de mi carrera, tanto en mi etapa como practicante como en el ámbito profesional. Existen más proyectos desarrollados en la empresa donde laboro, pero por políticas de privacidad no es posible compartir detalles de ellos.",        galeri: "",
        liveUrl: "",
        repoUrl: "",
    }
];
</script>

<style scoped>
.project-card {
    width: 95%;
    margin: 0 auto;
    background-color: rgb(19 21 26);
    padding: 0px;
    box-shadow: #cecece92 1.95px 1.95px 2.6px;
    border-radius: 10px;
}

.project-card:hover {
    box-shadow: #0dcaf0 1.95px 1.95px 2.6px;
}

.btnProyecto {
    background-color: rgb(19 21 26);
    color: #fff;
    border-color: #0dcaf0;
}
</style>
