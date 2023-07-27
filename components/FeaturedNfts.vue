<template>
  <section class="featured-nfts">
    <div class="nfter-container">
      <h2 class="featured-title">COLLECTION FEATURED NFTS</h2>
      <ul class="nfts">
        <li class="nft" v-for="(nft, i) in nfts" :key="name + i">
          <div class="gallery">
            <div
              class="main-img"
              :style="{
                'background-image': `url(../assets/images/nft-images/${nft.image})`,
              }"
            ></div>
            <ul class="images">
              <li
                class="small-img"
                v-for="(image, i) in nft.images"
                :key="image + i"
                :style="{
                  'background-image': `url(../assets/images/nft-images/${image})`,
                }"
              ></li>
            </ul>
          </div>
          <div class="nft-details">
            <h5 class="nft-name">{{ nft.name }}</h5>
            <div class="row">
              <div class="profile-photo"></div>
              <span>by Arkhan</span>
              <shared-action-button
                class="total"
                variant="secondary"
                text="Total 54 Items"
                size="xxs"
              />
            </div>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      nfts: [
        {
          name: "Amazing Collection",
          image: "nft-4.jpg",
          images: ["nft-3.jpg", "nft-2.jpg", "nft-7.jpg"],
        },
        {
          name: "Amazing Collection",
          image: "nft-4.jpg",
          images: ["nft-3.jpg", "nft-2.jpg", "nft-7.jpg"],
        },
        {
          name: "Amazing Collection",
          image: "nft-4.jpg",
          images: ["nft-3.jpg", "nft-2.jpg", "nft-7.jpg"],
        },
      ],
    };
  },
};
</script>

<style scoped>
.featured-nfts {
  height: 619px;
  backdrop-filter: blur(25px);
}

.nfter-container {
  padding: 65px 0;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.featured-title {
  font-family: "Archivo Black", sans-serif;
  font-size: 28px;
  font-weight: 700;
}

.nfts {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 1fr;
  gap: 3%;
  margin-top: 55px;
  flex-grow: 1;
}

.nft {
  display: grid;
  grid-template-rows: 8.9fr 2.1fr;
  gap: 5%;
}

.nft .gallery {
  display: grid;
  grid-template-columns: 7.3fr 2.7fr;
  grid-template-rows: 1fr;
  gap: 3%;
}

.nft .gallery .main-img {
  border-radius: 11px;
  background-size: cover;
  background-position: 50%;
}

.images {
  display: grid;
  grid-template-rows: 1fr 1fr 1fr;
  gap: 3%;
}

.images .small-img {
  border-radius: 11px;
  background-size: cover;
  background-position: 50%;
}

.nft-details {
  margin-top: 10px;
}

.nft-details .nft-name {
  font-size: 20px;
  font-weight: 700;
}

.nft-details .row {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 10px;
}

.total {
  margin-left: auto;
}

.nft-details .profile-photo {
  background-image: url(../assets/images/profile-photos/profile-1.jpg);
  height: 28px;
  width: 28px;
  border-radius: 100%;
  background-size: cover;
  background-position: 50%;
}
</style>