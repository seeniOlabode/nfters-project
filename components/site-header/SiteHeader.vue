<template>
  <header class="site-header">
    <div class="nfter-container">
      <div class="site-header_logo">NFTERS</div>
      <ul class="site-header_navigation-links">
        <li v-for="link in links" :key="link">
          <shared-site-link :text="link" />
        </li>
      </ul>
      <div class="site-header_left-side">
        <shared-search-component />
        <shared-action-button text="upload" />
        <shared-action-button text="connect wallet" variant="secondary" />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      links: ["Marketplace", "Resource", "About"],
    };
  },
};
</script>

<style scoped>
.site-header {
  border-bottom: solid 1px #efefef;
  height: 100px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.nfter-container {
  display: grid;
  grid-template-columns: auto 1fr auto;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.site-header_logo {
  font-family: "Archivo Black", sans-serif;
  font-size: 24px;
  color: var(--primary-color);
  border-right: solid 1px #efefef;
  height: 47px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 31px 0 0;
}

.site-header_navigation-links {
  list-style: none;
  display: flex;
  justify-content: center;
  margin: 0;
  padding: 0;
  gap: 47px;
}

.site-header_left-side {
  display: flex;
  justify-content: space-between;
  gap: 20px;
}
</style>