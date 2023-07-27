<template>
  <div class="large-showcase">
    <div class="nft-image"></div>
    <div class="nft-details">
      <div class="copy">
        <div class="profile-photo"></div>
        <div class="text">
          <h6 class="nft-detail-title">The Futr Abstr</h6>
          <p class="nft-detail-stock">10 in the stock</p>
        </div>
      </div>
      <div class="bid">
        <p>Highest Bid</p>
        <span class="bid-value">
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
                fill="#3A3A3A"
              />
            </g>
            <defs>
              <clipPath id="clip0_0_143">
                <rect
                  width="13"
                  height="21.3333"
                  fill="#3A3A3A"
                  transform="translate(0 0.512939)"
                />
              </clipPath>
            </defs>
          </svg>
          0.25 ETH</span
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.large-showcase {
  display: grid;
  grid-template-rows: 0.93fr 0.07fr;
  gap: 32px;
}

.large-showcase .nft-image {
  background-image: url(../assets/images/nft-images/nft-3.jpg);
  border-radius: 24px;
  background-size: cover;
  background-position: 50%;
}

.large-showcase .nft-details {
  /* padding-bottom: 20px; */
  display: flex;
  justify-content: space-between;
}

.nft-details .copy {
  display: flex;
  gap: 10px;
  align-items: center;
}

.copy .text {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.copy .nft-detail-title {
  font-size: 20px;
  font-weight: 700;
}

.copy .nft-detail-stock {
  font-size: 14px;
  color: #363639;
  font-weight: 400;
}

.nft-details .copy .profile-photo {
  width: 48px;
  height: 48px;
  aspect-ratio: 1/1;
  border-radius: 100%;
  background: url(../assets/images/profile-photos/profile-1.jpg);
  background-size: cover;
  background-position: 50%;
}

.bid p {
  font-size: 12px;
  font-weight: 500;
  color: #3a3a3a;
}

.bid .bid-value {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 10px;
  font-weight: 700;
  font-size: 16px;
  color: #3a3a3a;
}
</style>