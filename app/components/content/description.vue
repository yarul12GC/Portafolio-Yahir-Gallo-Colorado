<template>
    <div class="row">
        <div class="col-12 mx-auto px-4">
            <h4 class="fw-bold text-center" >{{ datosHeader.title }}</h4>
            <ul v-for="(desc, index) in datosHeader.description" :key="index">
                <p :class="desc.class"> {{ desc.parrafo }}
                </p>
            </ul>
        </div>
    </div>
</template>

<script setup lang="ts">
interface Description {
    parrafo: string
    class : string
}

interface HeaderData {
    title: string
    description: Description[]
}

// Definir los props con su tipo:
const props = defineProps<{
    datosHeader: HeaderData
}>()
</script>
