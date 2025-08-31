<template>
  <div class="row header py-3 px-4 ">
    <div class="col-10 col-md-6 my-auto">
      <h4 class="fw-bold">{{ datosHeader.title }}</h4>
    </div>
    <div class="col-2 d-block d-md-none my-auto">
      <a href="" class="btn p-0" @click.prevent="toggleMenu"> <img class="img-fluid" src="/img/menu.png" alt="Logo"
          width="30" height="30" />
      </a>
    </div>

    <div class="col-12 col-md-6 my-auto d-none d-md-block">
      <div class="row">
        <div class="col-12 col-md-6">
          <ul class="nav justify-content-end">
            <li class="nav-item" v-for="item in datosHeader.buttons" :key="item.name">
              <a class="nav-link" :href="item.url">{{ item.name }}</a>
            </li>

          </ul>
        </div>
        <div class="col-12 col-md-6">
          <ul class="nav justify-content-end">
            <li class="nav-item" v-for="item in datosHeader.redes" :key="item.name">
              <a class="nav-link" :href="item.url" target="_blank" rel="noopener">
                <img v-if="item.urlImg" :src="item.urlImg" alt="" width="24" height="24" />
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <div v-if="Isvisible" class="col-12 d-block d-md-none">
      <ul class="nav justify-content-center">
        <li class="nav-item" v-for="item in datosHeader.buttons" :key="item.name">
          <a class="nav-link">{{ item.name }}</a>
        </li>
      </ul>
    </div>
    <div v-if="Isvisible" class="col-12 d-block d-md-none">
      <ul class="nav justify-content-center">
        <li class="nav-item" v-for="item in datosHeader.redes" :key="item.name">
          <a class="nav-link" :href="item.url" target="_blank" rel="noopener">
            <img v-if="item.urlImg" :src="item.urlImg" alt="" width="24" height="24" />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">

interface Enlace {
  name: string
  url: string
  urlImg?: string
}

interface HeaderData {
  title: string
  buttons: Enlace[]
  redes: Enlace[]
}

const datosHeader: HeaderData = {
  title: "Ing. Yahir Gallo Colorado | Portafolio ",
  buttons: [
    { name: "Habilidades", url: "#skills" },
    { name: "proyectos", url: "#portafolio" },
    { name: "Contacto", url: "#contact" }
  ],
  redes: [
    {
      name: "Github",
      url: "https://github.com/yarul12GC",
      urlImg: "/img/github.png"
    },
    {
      name: "Linkedin",
      url: "https://www.linkedin.com/in/yahir-gallo-colorado-1956b32bb/",
      urlImg: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg"
    },
    {
      name: "Teléfono",
      url: "tel:7292870076",
      urlImg: "/img/llamar.png"
    }
  ]

}

const Isvisible = ref(false);

const toggleMenu = () => {
  Isvisible.value = !Isvisible.value
}
</script>

<style scoped>
.header {
  background-color: rgb(19 21 26);
  color: #dcdcdc;
}

.nav-link {
  color: #dcdcdc;
  cursor: pointer;

}
</style>
