<template>
  <div>
    <site-header />
    <main>
      <hero-section />
      <selling-points />
      <collection-showcase />
      <featured-nfts />
      <discover-nfts />
    </main>
  </div>
</template>

<script setup>
useHead({
  title: "NFTERS",
  link: [
    {
      rel: "preconnect",
      href: "https://fonts.googleapis.com",
    },
    {
      rel: "preconnect",
      href: "https://fonts.gstatic.com",
      crossorigin: true,
    },
    {
      href: "https://fonts.googleapis.com/css2?family=Archivo+Black&family=DM+Sans:wght@400;500;700&display=swap",
      rel: "stylesheet",
    },
  ],
});
</script>

<style>
</style>
