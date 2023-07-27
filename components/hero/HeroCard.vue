<template>
  <div
    class="hero-card"
    :style="{
      'background-image': `url(../../assets/images/nft-images/${cardData.image})`,
    }"
  >
    <div class="content">
      <div class="details">
        <h3 class="card-title">{{ cardData.title }}</h3>
        <div class="owner">
          <div
            class="profile-photo"
            :style="{
              'background-image':
                'url(../../assets/images/profile-photos/profile-1.jpg)',
            }"
          ></div>
          <h5 class="name">{{ cardData.name }}</h5>
        </div>
      </div>
      <div class="bidding">
        <div class="current-bid">
          <p>Current Bid</p>
          <div class="bid-value">
            <img src="../../assets/icons/eth.svg" alt="" />
            <span class="price">0.25 ETH</span>
          </div>
        </div>
        <div class="countdown">
          <p>Ends in</p>
          <div class="countdown-value">
            <span class="countdown-param"><span class="bold">12</span>h</span>
            <span class="countdown-param"><span class="bold">43</span>m</span>
            <span class="countdown-param"><span class="bold">42</span>s</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cardData: {
      type: Object,
      required: false,
      default: {
        title: "Abstr Gradient NFT",
        image: "nft-1.jpg",
        "profile-photo": "profile-1.jpg",
        name: "Arkhan17",
        price: "0.25 ETH",
      },
    },
  },
};
</script>

<style scoped>
.hero-card {
  aspect-ratio: 400/440;
  width: 400px;
  border-radius: 24px;
  background-size: cover;
  padding: 26px;
  color: white;
}

.content {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-title {
  margin: 0;
  font-size: 28px;
  font-weight: 700;
}

.owner {
  margin-top: 10px;
  display: flex;
  align-items: center;
  gap: 14px;
}

.profile-photo {
  aspect-ratio: 1/1;
  width: 32px;
  background-size: cover;
  background-position: 50% 50%;
  border-radius: 100%;
}

.name {
  margin: 0;
  font-size: 20px;
  font-weight: 700;
}

.bidding {
  width: 100%;
  height: 73px;
  background: blue;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(25px);
  padding: 14px 24px;
  display: flex;
  justify-content: space-between;
}

.current-bid,
.countdown {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.current-bid p,
.countdown p {
  font-size: 12px;
  font-weight: 500;
}

.bid-value {
  display: flex;
  align-items: center;
  gap: 10px;
}

.bid-value .price {
  font-size: 16px;
}

.countdown-value {
  display: flex;
  gap: 5px;
}

.countdown-param {
  font-weight: 500;
  font-size: 16px;
}

.countdown-param .bold {
  font-weight: 700;
}
</style>