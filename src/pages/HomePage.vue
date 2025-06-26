<template>
  <main>
    <h1 class="home-page-title">Bienvenue sur la page d'accueil !</h1>
    <div class="button-container">
      <BaseButton class="custom-margin"
        >BaseButton with custom margin</BaseButton
      >
      <BaseButton disabled>BaseButton disabled</BaseButton>
    </div>
  </main>
</template>

<script>
import BaseButton from "../components/BaseButton.vue";

export default {
  name: "HomePage",
  components: {
    BaseButton,
  },
};
</script>

<style scoped>
.home-page-title {
  text-align: center;
  font-size: 1.5rem;
}
.custom-margin {
  margin: 10px;
}
.button-container {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>