<template>
    <div class="cards-container">
      <CardComponent1
        v-for="(card, index) in cards"
        :key="index"
        :image="card.image"
        :title="card.title"
        @cardClick="showAlert"
      >
        {{ card.description }}
      </CardComponent1>
    </div>
  </template>
  
  <script setup>
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
    alert(`Bouton cliqué sur : ${title}`);
  };
  </script>
  
  <style scoped>
  .cards-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
  }
  </style>
  