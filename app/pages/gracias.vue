<template>
  <div class="row contgRACIAS mt-4">
    <div class="col-12 contenedor ">
    <div class="col-12 my-auto">
      <div class="gracias">
        <h2>¡Gracias por tu mensaje!</h2>
        <p>Me pondré en contacto contigo lo antes posible.</p>
      </div>
    </div>
    <div class="col-12 d-flex justify-content-center align-items-center my-auto">
      <NuxtLink to="/" class="btn">Volver al inicio</NuxtLink>
    </div>
    </div>

  </div>

</template>
<script setup>
definePageMeta({
  layout: "gracias",
});
</script>
<style scoped>
.gracias {
  text-align: center;
  margin-top: 100px;
  color: #fff;
}

.btn {
  margin-top: 20px;
  padding: 10px 20px;
  background: #417680;
  border-radius: 8px;
  color: #fff;
  text-decoration: none;
}
.btn:hover {
  background: #0dcaf0;
}
.contgRACIAS{
  height: 75vh;
}
</style>
