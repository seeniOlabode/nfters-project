<template>
  <ul class="grid grid-cols-4 gap-[2%]">
    <discover-nfts-discover-card v-for="nft in nfts" :key="nft + 'ahh'" />
  </ul>
</template>

<script>
import DiscoverCard from "./DiscoverCard.vue";
export default {
  components: { DiscoverCard },
  data() {
    return {
      nfts: [1, 2, 3, 4, 5, 6],
    };
  },
};
</script>

<style>
</style>