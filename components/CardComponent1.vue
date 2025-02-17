<script setup lang="ts">
// Type pour propriétés
type PropsType = {
  image: string;
  title: string;
};

const props = defineProps<PropsType>();

const emit = defineEmits(["cardClick"]);

const alerte = () => {
  console.log("Événement émis avec :", props.title);
  emit("cardClick", props.title);
};
</script>

<template>
  <div class="card">
    <img :src="image" alt="Image de la carte" class="card-image" />
    <div class="card-content">
      <h2>{{ title }}</h2>
      <p><slot></slot></p>
    </div>
    <button @click="alerte" class="card-button">Cliques ici</button>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  width: 300px;
  height: 370px;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  margin: 10px;
}

.card-image {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.card-content {
  padding: 15px;
}

button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #0056b3;
}
</style>
