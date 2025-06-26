<template>
  <button class="base-button">
    <slot />
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    variant: String,
  },
};
</script>

<style scoped>
.base-button {
  padding: 0.5em 1.2em;
  border: none;
  border-radius: 4px;
  background: #26a69a;
  color: white;
  font-size: 1rem;
  transition: background 0.2s;
}

.base-button:hover {
  background: #218e83;
  cursor: pointer;
}

.base-button:disabled {
  background: #26a69979;
  cursor: not-allowed;
}
</style> 