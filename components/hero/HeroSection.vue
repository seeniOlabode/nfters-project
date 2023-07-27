<template>
  <section class="hero-section">
    <div class="nfter-container">
      <div class="hero-copy">
        <h1>Discover, and collect Digital Art NFTs</h1>
        <p>
          Digital marketplace for crypto collectibles and non-fungible tokens
          (NFTs). Buy, Sell, and discover exclusive digital assets.
        </p>
        <shared-action-button class="main-cta" text="Explore Now" size="lg" />
        <ul class="analytics">
          <li
            v-for="analytic in analytics"
            :key="analytic.name + analytic.number"
            class="analytic"
          >
            <span class="number">{{ analytic.number }}K+</span>
            <span class="name">{{ analytic.name }}</span>
          </li>
        </ul>
        <div class="dotted-bg"></div>
      </div>
      <hero-card-deck />
    </div>
  </section>
</template>

<script>
import HeroCard from "./HeroCard.vue";
export default {
  components: { HeroCard },
  data() {
    return {
      analytics: [
        {
          number: "98",
          name: "Artwork",
        },
        {
          number: "12",
          name: "Auction",
        },
        {
          number: "15",
          name: "Artists",
        },
      ],
    };
  },
};
</script>

<style scoped>
.hero-section {
  overflow: hidden;
}
.hero-section .nfter-container {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  justify-content: center;
  width: 100vw;
  padding: 100px 0;
}

.hero-copy {
  max-width: 612px;
  position: relative;
}

.hero-copy h1 {
  font-family: "Archivo Black", sans-serif;
  text-transform: uppercase;
  font-size: 40px;
  line-height: 48px;
}

.hero-copy p {
  font-size: 20px;
  font-weight: 400;
  line-height: 32px;
  margin-top: 22px;
  max-width: 500px;
  color: #565656;
}

.main-cta {
  margin-top: 40px;
}

.analytics {
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0;
  margin-top: 40px;
  gap: 23px;
}

.analytic {
  display: flex;
  flex-direction: column;
}

.analytic .number {
  font-size: 40px;
  font-weight: 400;
  font-family: "Archivo Black", sans-serif;
  letter-spacing: 0.01em;
}

.analytic .name {
  color: #565656;
  font-size: 20px;
  font-weight: 400;
}

.dotted-bg {
  background-image: radial-gradient(#f4f4f4 4.5px, transparent 4.5px);
  background-size: 29px 29px;
  background-color: rgba(71, 212, 255, 0);
  height: 154px;
  width: 196px;
  position: absolute;
  left: -100px;
  bottom: 0;
  z-index: -1;
}
</style>