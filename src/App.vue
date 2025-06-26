<template>
  <div class="app">
    <BaseHeader />
    <HomePage class="home-page" />
    <BaseFooter />
  </div>
</template>

<script>
import HomePage from "./pages/HomePage.vue";
import BaseHeader from "./components/BaseHeader.vue";
import BaseFooter from "./components/BaseFooter.vue";
export default {
  name: "App",
  components: {
    HomePage,
    BaseHeader,
    BaseFooter,
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
}
.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.home-page {
  flex: 1;
}
</style>
