<template>
  <div>
    <AsyncButton :onClick="handleSignIn"
      >Se connecter avec Microsoft</AsyncButton
    >
    <div v-if="user">
      <p>Connecté en tant que : {{ user.name || user.username }}</p>
      <pre>{{ user }}</pre>
    </div>
  </div>
</template>

<script>
import { signInAndGetUser } from "../lib/microsoftGraph.js";
import AsyncButton from "./AsyncButton.vue";

export default {
  name: "SigninButton",
  components: { AsyncButton },
  data() {
    return {
      user: null,
    };
  },
  methods: {
    async handleSignIn() {
      try {
        const user = await signInAndGetUser();
        this.user = user;
        this.$emit("user-signed-in", user);
      } catch (e) {
        alert("Erreur lors de la connexion : " + e.message);
      }
    },
  },
};
</script> 