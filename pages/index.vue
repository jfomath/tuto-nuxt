<script setup lang="ts">
// Définition du type pour une carte
type Card = {
  image: string;
  title: string;
  description: string;
};

// Tableau typé de cartes
const cards: Card[] = [
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

// Fonction typée
const showAlert = (title: string): void => {
  alert(`Bouton cliqué sur : ${title}`);
};
</script>

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

<style scoped>
.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}
</style>
