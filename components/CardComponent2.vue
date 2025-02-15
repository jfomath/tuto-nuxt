<template>
    <v-card class="mx-auto my-4" max-width="300">
      <v-img :src="image" height="150px" cover></v-img>
      <v-card-title>{{ title }}</v-card-title>
      <v-card-text>
        <slot></slot>
      </v-card-text>
      <v-card-actions>
        <v-btn color="primary" elevation="4" variant="tonal" @click="alerte">Clique ici</v-btn>
      </v-card-actions>
    </v-card>
  </template>
  
  <script setup>
  const props = defineProps({
    image: String,
    title: String,
  });
  
  const emit = defineEmits(["cardClick"]);
  
  const alerte = () => {
    console.log("Événement émis avec :", props.title);
    emit("cardClick", props.title); // Transmettre l'événement au parent
  };
  </script>
  