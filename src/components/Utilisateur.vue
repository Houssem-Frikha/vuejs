<script setup>
import { ref } from 'vue';
const user = ref({
    email: "houssem.frikha22@gmail.com",
    adresse: "sakiet ezzit, sfax"
})
</script>
<template>
    <div class="container">
        <h1>{{ user.email }}</h1>
        <h3>Adresse: {{ user.adresse }} </h3>
    </div>
</template>
<style scoped></style>