<template>
  <div>
    <header class="d-block d-md-none">
      <commonHeader />
    </header>

    <main class="d-flex" id="main">
      <aside class="sidebar d-none d-md-block">
        <CommonSidebar />
      </aside>

      <div class="container-fluid sectionCustom">
        <NuxtPage />
        <commonFooter />
      </div>
    </main>
  </div>
</template>

<style scoped>
.sidebar {
  background-color: rgb(19, 21, 26);
  color: #dcdcdc;
  width: 20%;
  height: 100vh; /* Ocupa toda la altura de la ventana */
  overflow-y: auto; /* Scroll vertical solo en el sidebar */
  overflow-x: hidden;
  padding: 1rem;
  position: fixed;
  top: 0;
  left: 0;
  scroll-behavior: smooth; /* Desplazamiento suave */
}

/* 🎨 Scrollbar personalizado para navegadores basados en WebKit (Chrome, Edge, Safari) */
.sidebar::-webkit-scrollbar {
  width: 8px; /* Ancho del scrollbar */
}

.sidebar::-webkit-scrollbar-track {
  background: #141414; /* Color del fondo del track */
  border-radius: 10px;
}

.sidebar::-webkit-scrollbar-thumb {
  background: linear-gradient(180deg, #0dcaf0, #0a7c92); /* Gradiente de color */
  border-radius: 10px;
}

.sidebar::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(180deg, #11e3ff, #0dcaf0); /* Efecto al pasar el mouse */
}

/* 🦊 Compatibilidad con Firefox */
.sidebar {
  scrollbar-width: thin; /* Scroll delgado */
  scrollbar-color: #0dcaf0 #141414; /* (color de thumb, color de fondo) */
}

/* Ajustes del contenedor principal */
.sectionCustom {
  margin-left: 20%;
  width: 80%;
  padding: 1rem;
  overflow-x: hidden;
}

/* Modo responsive */
@media (max-width: 767px) {
  .sidebar {
    display: none;
  }

  .sectionCustom {
    margin-left: 0;
    width: 100%;
  }
}
</style>
