<template>
  <div class="base-layout">
    <BaseHeader :user="user" @userChanged="$emit('userChanged', $event)" />
    <main class="base-layout-content">
      <slot :user="user" />
    </main>
    <BaseFooter />
  </div>
</template>

<script>
import BaseHeader from "./BaseHeader.vue";
import BaseFooter from "./BaseFooter.vue";

export default {
  name: "BaseLayout",
  components: {
    BaseHeader,
    BaseFooter,
  },
  props: {
    user: {
      type: Object,
      default: null,
    },
  },
};
</script>

<style scoped>
.base-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.base-layout-content {
  flex: 1;
}
</style> 