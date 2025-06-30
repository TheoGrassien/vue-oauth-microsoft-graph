<template>
  <BaseLayout :user="user" @userChanged="onUserChanged">
    <HomePage class="home-page" :user="user" />
  </BaseLayout>
</template>

<script>
import HomePage from "./pages/HomePage.vue";
import BaseLayout from "./components/BaseLayout.vue";
export default {
  name: "App",
  components: {
    HomePage,
    BaseLayout,
  },
  data() {
    return {
      user: null,
    };
  },
  methods: {
    onUserChanged(user) {
      this.user = user;
    },
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
