<template>
  <main>
    <h1 class="home-page-title">Bienvenue sur la page d'accueil !</h1>
    <div class="button-container">
      <BaseButton class="custom-margin"
        >BaseButton with custom margin</BaseButton
      >
      <BaseButton disabled>BaseButton disabled</BaseButton>
      <BaseButton color="warn">BaseButton warn</BaseButton>
      <BaseButton color="danger">BaseButton danger</BaseButton>
      <AsyncButton
        class="custom-margin"
        :color="'primary'"
        :onClick="handleAsyncClick"
      >
        Disabled and animated for 2 seconds if clicked
      </AsyncButton>
    </div>
  </main>
</template>

<script>
import BaseButton from "../components/BaseButton.vue";
import AsyncButton from "../components/AsyncButton.vue";

export default {
  name: "HomePage",
  components: {
    BaseButton,
    AsyncButton,
  },
  methods: {
    handleAsyncClick() {
      // Retourne une promesse qui se résout après 2 secondes
      return new Promise((resolve) => {
        setTimeout(resolve, 2000);
      });
    },
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
  flex-direction: column;
  gap: 10px;
  align-items: center;
  justify-content: center;
}
</style>