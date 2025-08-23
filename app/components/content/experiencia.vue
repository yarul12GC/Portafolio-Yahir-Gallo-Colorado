<template>
    <div class="row">
        <div class="col-12 mt-3">
            <h4 class="fw-bold">{{ experiencia.title }}</h4>
        </div>
        <div class="col-12"> <span class="fw-bold">{{ experiencia.empresa }}</span>
        </div>
        <div class="col-12"> <span class="fw-small">{{ experiencia.fecha }}</span>
        </div>
        <div class="col-12">
            <div v-for="rol in experiencia.roles" :key="rol.name">
                <h5 class="text-warning">{{ rol.name }}</h5>
                <ul v-for="description in rol.description" :key="description.descriptionrol">
                    <p>{{ description.descriptionrol }}</p>
                </ul>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">

interface descriptionRoles {
    descriptionrol: string
}
interface roles {
    name: string,
    description: descriptionRoles[]
}
interface experiencia {
    title: string,
    empresa: string,
    fecha: string,
    roles: roles[]
}

const props = defineProps<{
    experiencia: experiencia
}>()
</script>