<template>
  <div class="row" id="contact">
    <div class="col-12 mx-auto conentForm">
      <CommonLoader v-if="cargando" />

      <h3>Escríbeme y me pondré en contacto contigo</h3>
      <form @submit.prevent="validarFormulario">

        <div class="row">
          <div class="col-12 col-md-6">
            <div class="form-group">
              <label class="form-label">Nombre completo</label>
              <input v-model="nombre" type="text" class="form-control" placeholder="Escribe tu nombre" />
              <small v-if="errores.nombre" class="text-danger">{{ errores.nombre }}</small>
            </div>
          </div>

          <div class="col-12 col-md-6">
            <div class="form-group">
              <label class="form-label">Email</label>
              <input v-model="email" type="email" class="form-control" placeholder="Escribe tu email" />
              <small v-if="errores.email" class="text-danger">{{ errores.email }}</small>
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-12 col-md-6">
            <div class="form-group">
              <label class="form-label">Teléfono</label>
              <input v-model="telefono" type="tel" class="form-control" placeholder="Escribe tu teléfono"
                maxlength="10" />
              <small v-if="errores.telefono" class="text-danger">{{ errores.telefono }}</small>
            </div>
          </div>
          <div class="col-12 col-md-6">
            <div class="form-group">
              <label class="form-label">Asunto</label>
              <input v-model="asunto" type="text" class="form-control" placeholder="Escribe tu asunto" />
              <small v-if="errores.asunto" class="text-danger">{{ errores.asunto }}</small>
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label class="form-label">Mensaje</label>
              <textarea v-model="mensaje" class="form-control" placeholder="Escribe tu mensaje"></textarea>
              <small v-if="errores.mensaje" class="text-danger">{{ errores.mensaje }}</small>
            </div>
          </div>
        </div>

        <div class="row mt-4">
          <div class="col-12 col-md">
            <button class="btn btn-primary w-100" type="submit">Enviar</button>
          </div>
          <div class="col-12 col-md-6">
            <a href="https://wa.me/+527292870076?text=Hola%20Yahir,%20vi%20tu%20portafolio%20y%20quiero%20contactarte"
              target="_blank" class="btn btn-success w-100">
              Enviar mensaje por WhatsApp
            </a>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { navigateTo } from "#app";

const nombre = ref("");
const email = ref("");
const telefono = ref("");
const asunto = ref("");
const mensaje = ref("");

const errores = ref<{ [key: string]: string }>({});

const regexEmail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
const regexTelefono = /^[0-9]{10}$/;

const cargando = ref(false);

const validarFormulario = async () => {
  errores.value = {};

  if (nombre.value.trim().length < 3) {
    errores.value.nombre = "El nombre debe tener al menos 3 caracteres.";
  }
  if (!regexEmail.test(email.value)) {
    errores.value.email = "Ingresa un correo válido.";
  }
  if (!regexTelefono.test(telefono.value)) {
    errores.value.telefono = "El teléfono debe tener 10 dígitos.";
  }
  if (asunto.value.trim().length < 3) {
    errores.value.asunto = "El asunto no puede estar vacío.";
  }
  if (mensaje.value.trim().length < 10) {
    errores.value.mensaje = "El mensaje debe tener al menos 10 caracteres.";
  }

  if (Object.keys(errores.value).length === 0) {
    try {
      cargando.value = true;
      await fetch("https://formsubmit.co/ajax/yahir634gallo@gmail.com", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          nombre: nombre.value,
          email: email.value,
          telefono: telefono.value,
          asunto: asunto.value,
          mensaje: mensaje.value,
        }),
      });

      navigateTo("/gracias");
    } catch (error) {
      console.error("Error al enviar el formulario:", error);
      alert("Hubo un problema al enviar tu mensaje. Inténtalo de nuevo.");
    } finally {
      cargando.value = false;
    }
  }
};
</script>

<style scoped>
.conentForm {
  background-color: rgb(19 21 26);
  padding: 20px;
  border-radius: 10px;
  box-shadow: #cecece92 1.95px 1.95px 2.6px;
}

.form-control {
  background-color: rgb(19 21 26);
  color: #fff;
  border-color: #0dcaf0;
}

.text-danger {
  font-size: 0.8rem;
  color: #f87171;
}
</style>
