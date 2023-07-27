<template>
  <div class="hero-card-deck">
    <hero-card
      class="hero-card"
      v-for="card in cards"
      :key="card"
      :data-position="
        card - activeCardIndex >= 0
          ? card - activeCardIndex
          : card - activeCardIndex + 4
      "
    />
    <hero-card class="hero-card-filler" />
    <div class="sticker">
      <svg viewBox="0 0 100 100" id="sticker-svg">
        <path
          id="path"
          d="m 50 0 a 10 10 0 1 0 0 100 A 10 10 0 1 0 50 0"
          fill="#ffe0d4"
        />
        <text>
          <textPath href="#path">LIVE AUCTION ● LIVE AUCTION ●</textPath>
        </text>
      </svg>
      <div class="eth">
        <svg
          width="13"
          height="22"
          viewBox="0 0 13 22"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_0_143)">
            <path
              d="M12.671 11.3796L6.50006 15.2463L0.325058 11.3796L6.50006 0.512939L12.671 11.3796ZM6.50006 16.4879L0.325058 12.6213L6.50006 21.8463L12.6751 12.6213L6.50006 16.4879Z"
              fill="black"
            />
          </g>
          <defs>
            <clipPath id="clip0_0_143">
              <rect
                width="13"
                height="21.3333"
                fill="black"
                transform="translate(0 0.512939)"
              />
            </clipPath>
          </defs>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [0, 1, 2, 3],
      activeCardIndex: 0,
    };
  },
  methods: {
    next() {
      const currentCard = select('[data-position="0"]');
      currentCard.classList.toggle("drop-card");

      setTimeout(() => {
        this.activeCardIndex =
          this.activeCardIndex >= 4 ? 1 : this.activeCardIndex + 1;
        currentCard.classList.toggle("drop-card");
      }, 1000);
    },
  },
  mounted() {
    this.interval = setInterval(() => {
      this.next();
    }, 3000);
  },
  beforeUnmount() {
    clearInterval(this.interval);
  },
};
</script>

<style scoped>
.hero-card-deck {
  display: flex;
  position: relative;
}

.hero-card-filler {
  visibility: hidden;
}

.hero-card:not(.hero-card-filler) {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  transition: transform 0.2s;
  transform-origin: center;
}

.hero-card[data-position="0"] {
  z-index: 4;
}

.hero-card[data-position="1"] {
  transform: translateX(40px) scale(0.9);
  z-index: 3;
}

.hero-card[data-position="2"] {
  transform: translateX(80px) scale(0.8);
  z-index: 2;
  transition: none;
}

.hero-card[data-position="3"] {
  transition: none;
  z-index: 1;
  opacity: 0;
}

.drop-card {
  z-index: 100;
  animation: drop-animation 1s cubic-bezier(1, 0, 0, 1);
}

@keyframes drop-animation {
  from {
    transform: translateY(-10px);
  }
  to {
    transform: translateY(-10px);
  }
  to {
    transform: translateY(200%) rotate(-15deg);
  }
}

.sticker {
  width: 101px;
  height: 101px;
  aspect-ratio: 1/1;
  background: #ffe0d4;
  border-radius: 100%;
  position: absolute;
  left: -50px;
  bottom: 100px;
  z-index: 10000;
  display: flex;
  align-items: center;
  justify-content: center;
}

#sticker-svg {
  scale: 0.7;
  transform: rotate(0);
  animation: stickerAnimation 5s infinite linear;
}

#sticker-svg text {
  font-size: 1em;
  letter-spacing: 5px;
  font-weight: 400;
}

.eth {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

@keyframes stickerAnimation {
  to {
    transform: rotate(360deg);
  }
}
</style>