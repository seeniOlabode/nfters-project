<template>
  <NuxtLink class="site-link">
    <span class="site-link_space-filler">{{ text }}</span>
    <span class="site-link_animation-container">
      <span class="site-link_text">{{ text }}</span>
      <span class="site-link_text">{{ text }}</span>
    </span>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
      default: "Link",
    },
  },
};
</script>

<style scoped>
.site-link {
  display: inline-block;
  position: relative;
  font-size: 16px;
  overflow: hidden;
  cursor: pointer;
  text-transform: capitalize;
}

.site-link_space-filler {
  visibility: hidden;
}

.site-link_animation-container {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease-in;
  transform: translateY(0) rotate(0);
}

/* HOVER STATE STYLES */

.site-link:hover .site-link_animation-container {
  transform: translateY(-50%);
}
</style>