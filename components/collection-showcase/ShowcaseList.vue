<template>
  <ul class="showcase-list">
    <li class="nft" v-for="nft in showcaseNfts" :key="nft.name + nft.price">
      <div
        class="nft-image"
        :style="{
          'background-image': `url(../../assets/images/nft-images/${nft.image})`,
        }"
      ></div>
      <div class="nft-details">
        <h6>{{ nft.name }}</h6>
        <div class="row">
          <div
            class="profile-photo"
            :style="{
              'background-image': `url(../../assets/images/profile-photos/${nft.profile})`,
            }"
          ></div>
          <span class="price">
            <svg
              width="13"
              height="22"
              viewBox="0 0 13 22"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <g clip-path="url(#clip0_0_143)">
                <path
                  d="M12.671 11.3796L6.50006 15.2463L0.325058 11.3796L6.50006 0.512939L12.671 11.3796ZM6.50006 16.4879L0.325058 12.6213L6.50006 21.8463L12.6751 12.6213L6.50006 16.4879Z"
                  fill="#00AC4F"
                />
              </g>
              <defs>
                <clipPath id="clip0_0_143">
                  <rect
                    width="13"
                    height="21.3333"
                    fill="#00AC4F"
                    transform="translate(0 0.512939)"
                  />
                </clipPath>
              </defs>
            </svg>

            {{ nft.price }}
          </span>
          <span class="index">1 of 8</span>
        </div>
        <shared-action-button
          class="place-bid"
          text="place a bid"
          size="xs"
          variant="secondary"
        />
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      showcaseNfts: [
        {
          name: "The Futr Abstr",
          price: "0.25 ETH",
          image: "nft-4.jpg",
          profile: "profile-1.jpg",
        },
        {
          name: "The Futr Abstr",
          price: "0.25 ETH",
          image: "nft-5.jpg",
          profile: "profile-1.jpg",
        },
        {
          name: "The Futr Abstr",
          price: "0.25 ETH",
          image: "nft-6.jpg",
          profile: "profile-1.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.showcase-list {
  margin: 0;
  padding: 0;
  list-style: none;
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  gap: 5%;
}

.showcase-list .nft {
  display: flex;
  gap: 20px;
  align-items: center;
}

.showcase-list .nft .nft-image {
  height: 147px;
  aspect-ratio: 1/1;
  border-radius: 12px;
  background-size: cover;
  background-position: 50%;
}

.showcase-list .nft-details h6 {
  font-size: 20px;
  font-weight: 700;
}

.nft-details .row {
  display: flex;
  gap: 8px;
  margin-top: 10px;
  align-items: center;
}

.nft-details .row .profile-photo {
  width: 34px;
  height: 34px;
  aspect-ratio: 1/1;
  background-size: cover;
  background-position: 50%;
  border-radius: 100%;
}

.nft-details .row .price {
  color: #00ac4f;
  border: solid 1px #00ac4f;
  border-radius: 6px;
  font-size: 12px;
  font-weight: 700;
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 0 8px;
}

.nft-details .row .price svg {
  width: 8.53px;
}

.nft-details .row .index {
  color: #757575;
  font-size: 14px;
}

.nft-details .place-bid {
  margin-top: 16px;
}
</style>