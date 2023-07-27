<template>
  <section class="collections-showcase hidden">
    <div class="nfter-container">
      <div class="showcase">
        <collection-showcase-large-showcase />
        <collection-showcase-list />
      </div>
      <div class="top-collections">
        <h5 class="title">TOP COLLECTIONS OVER</h5>
        <span class="duration">Last 7 days</span>
        <ul class="collection-list">
          <li
            v-for="(collection, i) in topCollections"
            :key="collection.name + growth"
            class="collection"
          >
            <span class="index">{{ i + 1 }}</span>
            <span
              class="nft-image"
              :style="{
                'background-image': `url(../../assets/images/nft-images/${collection.img}.jpg)`,
              }"
            >
              <img
                v-if="collection.verified"
                class="verified"
                src="../../assets/icons/verify.svg"
                alt=""
              />
            </span>
            <div class="name-volume">
              <span class="collection-name">{{ collection.name }}</span>
              <span class="collection-volume">
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

                {{ collection.volume }}</span
              >
            </div>
            <span
              class="collection-growth"
              :class="collection.growth > 1 ? 'green' : 'red'"
            >
              {{ collection.growth > 1 ? "+" : "" }}
              {{ collection.growth }}%
            </span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      topCollections: [
        {
          name: "CryptoFunks",
          volume: "19,769.39",
          growth: 26.52,
          verified: true,
          img: "nft-8",
        },
        {
          name: "Cryptix",
          volume: "2,799.39",
          growth: -10.52,
          verified: false,
          img: "nft-7",
        },
        {
          name: "Frensware",
          volume: "9,267.39",
          growth: 1.52,
          verified: false,
          img: "nft-6",
        },
        {
          name: "BalloonsVille",
          volume: "10,050,344.5",
          growth: 50,
          verified: true,
          img: "nft-5",
        },
        {
          name: "CryptoFunks",
          volume: "19,769.39",
          growth: 26.52,
          verified: true,
          img: "nft-8",
        },
      ],
    };
  },
};
</script>

<style scoped>
.collections-showcase {
  height: 808px;
  padding: 134px 0;
}

.nfter-container {
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-columns: 7fr 3fr;
  grid-template-rows: 1fr;
}

.showcase {
  display: grid;
  grid-template-columns: 5.5fr 4.5fr;
  grid-template-rows: 1fr;
  gap: 5%;
}

.top-collections {
  border-left: solid 1px #ececec;
  padding-left: 42px;
  display: grid;
  grid-template-rows: auto auto 1fr;
}

.top-collections .title {
  font-family: "Archivo Black", sans-serif;
  font-size: 20px;
}

.top-collections .duration {
  color: #3d00b7;
  font-weight: 700;
  font-size: 18px;
  margin-top: 10px;
  display: inline-block;
}

.collection-list {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
}

.collection-list .collection {
  display: grid;
  grid-template-columns: 10px auto auto auto;
  align-items: center;
  gap: 25px;
}

.collection-list .collection:not(:last-child) {
  border-bottom: solid 1px #f0f0f0;
}
.collection-list .collection .index {
  font-size: 24px;
  font-weight: 700;
}

.collection-list .collection .nft-image {
  width: 60px;
  height: 60px;
  aspect-ratio: 1/1;
  display: inline-block;
  background-size: cover;
  background-position: 50%;
  border-radius: 100%;
  position: relative;
}

.collection .verified {
  position: absolute;
  display: inline-block;
  right: -10px;
  top: -5px;
}

.name-volume {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 10px;
}

.name-volume .collection-name {
  font-size: 16px;
  font-weight: 500;
}

.name-volume .collection-volume {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 14px;
  font-weight: 700;
  color: #636363;
}

.collection-growth {
  display: inline-block;
  margin-left: auto;
  font-size: 18px;
  font-weight: 700;
  white-space: nowrap;
}

.green {
  color: #14c8b0;
}

.red {
  color: #ff002e;
}
</style>