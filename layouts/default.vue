<template>
  <div class="layout">
    <header>
      <h1>EXERCICES AVEC DES CARTES</h1>
    </header>

    <main>
      <slot />
    </main>

    <footer>
      <p>KIRAGO © 2025</p>
    </footer>
  </div>
</template>

<style scoped>

/* Assure que la page prend toute la hauteur de l'écran */
.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Le main prend toute la place disponible pour pousser le footer en bas */
main {
  flex: 1;
  padding: 20px;
}

/* Style du header et du footer */
header {
  background: #007bff;
  color: white;
  padding: 15px;
  text-align: center;
}

footer {
  background: #f1f1f1;
  padding: 10px;
  text-align: center;
}
</style>
