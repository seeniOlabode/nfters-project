<template>
  <section class="discover-section">
    <div class="nfter-container py-[64px]">
      <h2 class="featured-title text-[28px] font-[700] font-archivo uppercase">
        DISCOVER MORE NFTS
      </h2>

      <shared-multi-select
        class="mt-[40px]"
        @options="(value) => (options = value)"
      />
      <discover-nfts-discover-grid class="mt-[40px]" />
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      options: {},
    };
  },
  methods: {
    handleOptions(value) {
      console.log(value);
    },
  },
};
</script>

<style>
</style>