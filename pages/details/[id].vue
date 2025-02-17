<script setup>
const route = useRoute();

const id = route.params.id;
</script>

<template>
  <div>
    <h1>Détails de la  {{ id }}</h1>
    <p>Affiche ici toutes les infos pour l'élément avec l'ID {{ id }}.</p>
  </div>
</template>
