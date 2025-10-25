<template>
  <div class="row">
    <div class="col-12 my-auto d-flex justify-content-center">
      <div class="classImg">
        <img :src="data.imgDeveloper" alt="Foto de desarrollador" class="img-fluid" width="180" />
      </div>
    </div>

    <div class="col-12 text-center mt-3">
      <h3>{{ data.title }}</h3>
      <p class="h5 text-muted">{{ data.description }}</p>
      <p class="text-secondary">{{ data.location }}</p>
    </div>
    <div class="col-12">
      <span class="text-center d-block text-uppercase fw-semibold text-info">
        Secciones
      </span>

      <div class="d-flex flex-wrap justify-content-center gap-3 mt-2">
        <div v-for="item in data.section" :key="item.name">
          <a :href="item.url" class="btn btnContenido text-decoration-none px-4">
            {{ item.name }}
          </a>
        </div>
      </div>
    </div>

    <div class="col-12">
      <span class="text-center d-block text-uppercase fw-semibold text-info">
        Contactame</span>
      <div class="d-flex flex-wrap justify-content-center gap-2 mt-3">
        <div v-for="item in data.butons" :key="item.name">
          <a :href="item.url" target="_blank" :class="item.classBtn" class="btn text-decoration-none px-3">
            {{ item.name }}
          </a>
        </div>
      </div>
    </div>

    




  </div>
</template>

<script setup lang="ts">
interface Title {
  title: string;
  description: string;
  imgDeveloper: string;
  location: string;
  section: { name: string; url: string }[];
  butons: { name: string; url: string; icon?: string; classBtn?: string }[];
}

const data: Title = {
  title: "Ing. Yahir Gallo Colorado",
  description: "Desarrollador Web Frontend",
  imgDeveloper: "/img/devfs.jpg",
  location: "México, Zinacantepec estado de Mexico",
  section: [
    { name: "Habilidades", url: "#skills" },
    { name: "proyectos", url: "#portafolio" },
    { name: "Contacto", url: "#contact" },
    { name: "Experiencia", url: "#experiencia" },
    { name: "Inicio", url: "#main" },
  ],
  butons: [
    { name: "Github", url: "https://github.com/yarul12GC", classBtn: "btn-github" },
    { name: "Linkedin", url: "https://www.linkedin.com/in/yahir-gallo-colorado-1956b32bb/", classBtn: "btn-linkedin" },
    { name: "Teléfono", url: "tel:7292870076", classBtn: "btn-whatsapp" },
  ],
};
</script>

<style scoped>
.classImg {
  border-radius: 50%;
  overflow: hidden;
  border: solid 5px #0dcaf0;
}

ul li {
  font-size: 0.9rem;
  color: #666;
}

.btn-linkedin {
  background-color: #0e76a8 ! important;
  color: #fff ! important;
}

.btn-github {
  background-color: #333 ! important;
  color: #fff ! important;
}

.btn-whatsapp {
  background-color: #25D366 ! important;
  color: #fff ! important;
}

.btnContenido {
  color: #fff ! important;
}

.btnContenido:hover {
  color: #fff ! important;
  text-decoration: underline ! important;
}
</style>
