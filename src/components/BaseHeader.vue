<template>
  <header class="base-header">
    <div class="header-left">
      <i class="fas fa-home"></i>
      <span>Home</span>
    </div>
    <div class="header-right">
      <i class="fas fa-user"></i>
      <template v-if="userStore.user">
        <span
          >Connecté en tant que :
          {{ userStore.user.name || userStore.user.username }}</span
        >
      </template>
      <template v-else>
        <SigninButton />
      </template>
    </div>
  </header>
</template>

<script>
import SigninButton from "./SigninButton.vue";
import { useUserStore } from "../lib/userStore.js";

export default {
  name: "BaseHeader",
  components: { SigninButton },
  setup() {
    const userStore = useUserStore();
    return { userStore };
  },
};
</script>

<style scoped>
.base-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #26a69a;
  color: #222;
  padding: 16px 32px;
  font-family: Arial, sans-serif;
}
.header-left,
.header-right {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}
.header-right {
  font-weight: 500;
}
.base-header i {
  font-size: 1.2rem;
}
</style>
