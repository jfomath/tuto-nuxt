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
  import { useRouter } from 'vue-router';
  const router = useRouter();
  
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
  
  const showAlert = (id) => {
    $swal.fire({
      title: "Détails de la carte",
    text: "Voulez-vous voir plus de détails ?",
    icon: "info",
    showCancelButton: true,
    confirmButtonText: "Voir plus",
    cancelButtonText: "Annuler",
      customClass: {
    confirmButton: "btn-ok"
  }
    }).then((result) => {
    if (result.isConfirmed) {
      router.push(`/details/${id}`); // Redirection Nuxt 3
    }
  });
  };
  </script>

  <style>
  .btn-ok {
  background-color: #28a745 !important;
  color: white !important;
  border-radius: 5px;
  padding: 10px 20px;
  font-size: 16px;
}
  </style>
  