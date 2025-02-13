<template>
    <v-container>
      <v-row>
        <v-col v-for="(card, index) in cards" :key="index" cols="12" md="4">
          <CardComponent2
            :image="card.image"
            :title="card.title"
            @cardClick="showAlert"
          >
            {{ card.description }}
          </CardComponent2>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script setup>
  
  const { $swal } = useNuxtApp();
  
  const cards = [
    {
      image: "/images/img1.png",
      title: "Carte 1",
      description: "Ceci est la description de la première carte.",
    },
    {
      image: "/images/img2.png",
      title: "Carte 2",
      description: "Voici une autre carte avec une description différente.",
    },
    {
      image: "/images/img3.png",
      title: "Carte 3",
      description: "Encore une autre carte intéressante à regarder.",
    },
  ];
  
  const showAlert = (title) => {
    $swal.fire({
      title: `Bouton cliqué !`,
      text: `Vous avez cliqué sur : ${title}`,
      icon: "success",
      confirmButtonText: "OK",
    });
  };
  </script>
  