<template>
  <button class="site-button" :class="[variant, size]">
    <span class="site-button_animation-container">
      <span class="site-button_animation-container_inner-container">
        <span class="site-button_text">{{ text }}</span>
        <span class="site-button_text">{{ text }}</span>
      </span>
      <span class="site-button_space-filler">
        {{ text }}
      </span>
    </span>
  </button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
      default: "",
    },
    variant: {
      type: String,
      required: false,
      default: "primary",
    },
    size: {
      type: String,
      required: false,
      default: "s",
    },
  },
};
</script>

<style scoped>
.site-button {
  background: none;
  border: none;
  text-transform: capitalize;
  font-weight: 700;
  font-size: 14px;
  height: 50px;
  min-width: 131px;
  border-radius: 60px;
  padding: 0 22px;
  cursor: pointer;
  position: relative;
}

.site-button.lg {
  font-size: 20px;
  height: 65px;
  padding: 0 40px;
}

.site-button.xs {
  height: 45px;
  padding: 0 20px;
}

.site-button.xxs {
  height: 29px;
  font-size: 11px;
  padding: 0 11px;
  min-width: unset;
}

.primary {
  background-color: var(--primary-color);
  color: white;
}

.secondary {
  border: solid 2px var(--primary-color);
  color: var(--primary-color);
}

/* FANCY STUFF */

.site-button_space-filler {
  visibility: hidden;
}

.site-button_animation-container {
  overflow: hidden;
  display: inline-block;
  position: relative;
}

.site-button_animation-container_inner-container {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  display: flex;
  flex-direction: column;
  transition: transform 0.2s ease-in;
}

.site-button_animation-container .site-button_text {
  flex-basis: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* HOVER STYLES */

.site-button:hover .site-button_animation-container_inner-container {
  transform: translateY(-50%);
}
</style>