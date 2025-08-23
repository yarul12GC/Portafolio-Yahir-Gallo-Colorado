<template>
  <div class="row">
    <div class="col-12">
      <div class="row mt-4 contenedor">
        <div class="col-12 pb-3">
          <h3 class="fw-bold colorT">Acerca de mi</h3>
        </div>
        <div class="col-12">
          <div class="row">
            <div class="col-12 col-md-5 my-auto">
              <ContentImgs />
            </div>

            <div class="col-12 col-md-7 my-auto ">
              <ContentDescription :datosHeader="datosHeader" />
            </div>
          </div>

        </div>
      </div>

      <div class="row mt-4 contenedor">
        <div class="col-12">
          <h3 class="fw-bold colorT">Mis Estudios</h3>
        </div>
        <div class="row">
          <div class="col-12 col-md-6">
            <ContentDescription :datosHeader="datoseSTUDIOS" />
          </div>
          <div class="col-12 col-md-6">
            <ContentDescription :datosHeader="datoseSTUDIOS2" />
          </div>
        </div>
      </div>
      <div class="row mt-4 contenedor2">
        <div class="col-12">
          <h3 class="fw-bold colorT">Mis Habilidades</h3>
        </div>
        <div class="col-12">
          <div class="row">
            <div class="col-12">
              <CommonHabilidades />
            </div>
          </div>
        </div>
      </div>

      <div class="row mt-4 contenedor">
        <div class="col-12">
          <h3 class="fw-bold colorT">Mi experiencia profesional</h3>
        </div>
        <div class="col-12">
          <ContentExperiencia :experiencia="experienciaAhorra" />
        </div>
        <div class="col-12">
          <ContentExperiencia :experiencia="experienciaCencaComex" />
        </div>
        <div class="col-12">
          <ContentExperiencia :experiencia="experienciaBecario" />
        </div>
      </div>

      <div class="row mt-4 contenedor2">
        <div class="col-12">
          <h3 class="fw-bold colorT">Mis Proyectos</h3>
        </div>
        <div class="col-12">
          <ContentPortafolio />
        </div>
      </div>

      <div class="row mt-4 contenedor2">
        <div class="col-12">
          <h3 class="fw-bold colorT">Contactame</h3>
        </div>
        <div class="col-12 col-md-10 col-lg-8 mx-auto ">
          <FormContacto />
        </div>
      </div>
      <div class="col-12 mt-4 contenedor2">
      <FormMediosContacto />  
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">

definePageMeta({
  layout: "principal",
});

const datosHeader = {
  title: "Ing. Yahir Gallo Colorado. ",
  description: [
    { parrafo: "soy ingeniero en Entornos Virtuales y Negocios Digitales, con un enfoque actual en el desarrollo web. Me considero una persona proactiva, resolutiva y extrovertida, con facilidad para comunicarme, trabajar en equipo y asumir roles de liderazgo cuando se necesita. Tengo experiencia en el diseño y desarrollo de aplicaciones web, cuidando siempre aspectos como el rendimiento, las buenas prácticas y la escalabilidad. Disfruto enfrentar nuevos retos, adaptarme a distintos entornos y buscar soluciones creativas que realmente aporten valor.", class: "colorT" },
  ]
}

const datoseSTUDIOS = {
  title: "",
  description: [
    {
      parrafo: "Ingeniero en Entornos Virtuales y Negocios Digitales",
      class: "fw-bold  fs-5 mb-0 p-0 text-start color"
    },
    { parrafo: "univercidad Tecnologica de Zinacantepec", class: "fw-small" },
    { parrafo: "2022 - 2024 (Titulado)", class: "fw-small" },
  ]
}

const datoseSTUDIOS2 = {
  title: "",
  description: [
    {
      parrafo: "Tecnico Superior en Tecnologias de la Informacion Area Entonos Virtuales y Negocios Digitales",
      class: "fw-bold  fs-5  mb-0 p-0 text-start color"
    },
    {
      parrafo: "univercidad Tecnologica de Zinacantepec",
      class: "fw-small"
    },
    { parrafo: "2020 - 2022 (Titulado)", class: "fw-small" },
  ]
}

const experienciaAhorra = {
  title: "Desarollador web Front-End",
  empresa: "Ahorra Seguros",
  fecha: "Noviembre 2024 -  Actualidad",
  roles: [
    {
      name: "Soporte, mantenimiento e implementación de servicios en motores de emisión y cobros",
      description: [
        { descriptionrol: "Me he encargado del mantenimiento de los diferentes motores de cobro y emisión de pólizas de distintas aseguradoras." },
        { descriptionrol: "También eh realizado la implementación de nuevos servicios de cobro y emisión, modificando flujos y optimizando procesos mediante Vue 3, Pinia y Axios." },
      ]
    }
    ,
    {
      name: "Maquetación y desarrollo de nuevos proyectos:",
      description: [
        { descriptionrol: "Me he encargado del desarrollo front-end de nuevos proyectos, desde la maquetación basada en prototipos estáticos hasta la implementación funcional utilizando el framework Nuxt3. En particular, trabajé en un sistema de inspecciones con gestión de usuarios por rangos de privilegios, integrando servicios del backend (GET, POST, PUT) para funcionalidades como login, visualización de datos y gestión de información." },
        { descriptionrol: "Además, desarrollé interfaces dinámicas personalizadas, que muestran colores, logotipos y filtros específicos según el tipo de usuario y la aseguradora correspondiente, mejorando la experiencia de uso. También participé en el desarrollo de un sitio para gastos médicos, que permite cotizar diferentes paquetes, enviar la información al backend y mostrar los detalles y precios de cada opción de forma clara y ordenada." },
      ]
    },
    {
      name: "Implementación de nuevas funcionalidades en los sitios actuales:",
      description: [
        { descriptionrol: " Me he encargado de consumir e integrar nuevos servicios en las landing pages existentes. Un ejemplo de ello es la implementación de un servicio que muestra dinámicamente el nombre del asesor telefónico en la página." },
        { descriptionrol: " También realicé la validación del servicio de autenticación para evitar ciclos innecesarios en las peticiones que requieren un token de acceso optimizando así el rendimiento y la seguridad en las llamadas a API." },
      ]
    },
    {
      name: "Soporte y mantenimiento",
      description: [
        { descriptionrol: "Me he encargo de la gestión y soporte técnico de 120 landing pages activas, realizando actualizaciones y mejoras de manera constante. Uso features y hotfixes para optimizar el rendimiento y asegurar que todo funcione correctamente, trabajando con herramientas de control de versiones como Git, SourceTree y Bitbucket." },
      ]
    },
    {
      name: "Migraciones",
      description: [
        { descriptionrol: "Realice migración de 8 landing pages de Nuxt2 a Nuxt3,  para asegurar una experiencia moderna y fluida. Durante este proceso, garantizo que los sitios sean totalmente responsivos, aprovechando Bootstrap y CSS." },
      ]
    },
  ],
}

const experienciaCencaComex = {
  title: "Desarollador web Full Stack",
  empresa: "CENCA COMERCIO EXTERIOR",
  fecha: "Enero 2024 - Noviembre 2024",
  roles: [
    {
      name: "Sistema de captura de PEDIMENTO",
      description: [
        { descriptionrol: "Desarrollé un sistema integral para la captura de pedimentos en los cursos de la empresa, reemplazando un proceso basado en Excel." },
        { descriptionrol: "El sistema incluyó más de 30 módulos, permitía ingresar datos y generaba automáticamente un PDF con códigos de barras y QR." },
        { descriptionrol: "Me encargué de todo el ciclo de desarrollo: diseño de interfaz, lógica de flujo, creación de la base de datos, backend, frontend y despliegue final." }
      ]
    },
    {
      name: "Sistema CERTICENCA",
      description: [
        { descriptionrol: "Diseñé y desarrollé un sistema para asignar materiales y certificados a los usuarios según el curso o diplomado realizado." },
        { descriptionrol: "Me ocupé de todo el proceso: diseño de la interfaz, lógica de negocio, base de datos y despliegue." },
        { descriptionrol: "Utilicé PHP, HTML5, CSS, JavaScript y Bootstrap para construir una plataforma funcional, intuitiva y atractiva." }
      ]
    },
    {
      name: "Sistema CESSITCENCA",
      description: [
        { descriptionrol: "Lideré y colaboré en el desarrollo de un sistema de gestión de inventarios automatizado, alineado con el Anexo 24 de las reglas de comercio exterior." },
        { descriptionrol: "Me encargué del desarrollo completo de los módulos en backend y frontend, además de supervisar el despliegue final." }
      ]
    },
    {
      name: "Reestructuración de la página principal",
      description: [
        { descriptionrol: "Rediseñé y finalicé la página principal de la empresa en WordPress, mejorando su funcionalidad, diseño y experiencia de usuario." }
      ]
    }
  ]
}

const experienciaBecario = {
  title: "Becario de desarrollo web",
  empresa: "Universidad Alfa Lambda S.L. ",
  fecha: "mayo 2022 - septiembre 2022",
  roles: [
    {
      name: "Mantenimiento de páginas web",
      description: [
        { descriptionrol: "Realicé mantenimiento y gestión de páginas web en WordPress, asegurando su correcta funcionalidad." },
        { descriptionrol: "Optimizaba el contenido para mejorar la experiencia de usuario y garantizar un mejor rendimiento." }
      ]
    },
    {
      name: "Sistema CERTITUAL",
      description: [
        { descriptionrol: "Participé en el desarrollo de un sistema para la emisión de títulos y certificados electrónicos en formato XML." },
        { descriptionrol: "Mi principal responsabilidad fue el diseño y desarrollo de la interfaz de usuario, garantizando usabilidad y eficiencia." }
      ]
    },
    {
      name: "Chatbot institucional",
      description: [
        { descriptionrol: "Desarrollé un chatbot integral para todos los planteles de la universidad." },
        { descriptionrol: "El chatbot facilitaba la comunicación y brindaba soporte eficiente a estudiantes y futuros prospectos." }
      ]
    },
    {
      name: "Soporte técnico y redes",
      description: [
        { descriptionrol: "Realicé armado de cables de red, configuración de repetidores y switches." },
        { descriptionrol: "Implementé conexiones de red con filtrado de direcciones MAC para mayor seguridad." }
      ]
    }
  ]
} 
</script>
