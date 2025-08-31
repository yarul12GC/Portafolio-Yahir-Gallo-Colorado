<template>
    <div class="row">
        <div class="col-12">
            <h4 class="text-start mb-4 colorT ">Tambien me puedes contactar por estos medios</h4>
        </div>
        <div class="col-6 col-md-3 col-lg-3 " v-for="contacto in contactos" :key="contacto.titulo">
            <div class="d-flex justify-content-center">
                <div class="card-icon"><a :href="contacto.link" target="_blank" rel="noopener">
                        <img :src="contacto.icono" :alt="contacto.titulo" width="24" height="24" />
                    </a></div>
            </div>

        </div>

    </div>
</template>
<script setup lang="ts">
interface DataMedioContracto {
    titulo: string,
    icono: string,
    link: string

}

const contactos = ref<DataMedioContracto[]>([
    {
        titulo: "Github",
        icono: "/img/github.png",
        link: "https://github.com/yarul12GC"
    },
    {
        titulo: "Linkedin",
        icono: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg",
        link: "https://www.linkedin.com/in/yahir-gallo-colorado-1956b32bb/"
    },
    {
        titulo: "Correo",
        icono: "/img/gmail.png",
        link: "mailto:yahir634gallo@gmail.com"
    },
    {
        titulo: "Telefono",
        icono: "/img/llamar.png",
        link: "tel:7292870076"
    }
])
</script>
<style scoped>
.card-icon {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: radial-gradient(circle at 50% 50%, rgba(13, 202, 240, 0.22), rgba(13, 202, 240, 0.06));
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(2px);
    border: 1px solid rgba(13, 202, 240, 0.24);
    cursor: pointer;
}
.card-icon:hover {
    border: 1px solid rgb(255, 255, 255);
}
</style>