<template>
  <section class="selling-points">
    <div class="nfter-container">
      <h3 class="section-title">The amazing NFT art of the world here</h3>
      <ul class="points">
        <li v-for="point in points" :key="point.title + icon" class="point">
          <img class="icon" :src="`../assets/icons/${point.icon}`" alt="" />
          <h5 class="title">{{ point.title }}</h5>
          <p class="description">{{ point.description }}</p>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      points: [
        {
          title: "Fast Transactions",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam etiam viverra tellus imperdiet.",
          icon: "card-tick.svg",
        },
        {
          title: "Growth Transaction",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam etiam viverra tellus imperdiet.",
          icon: "chart-square.svg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.selling-points {
  background-color: rgba(217, 224, 236, 0.2);
  backdrop-filter: blur(25px);
}
.selling-points .nfter-container {
  height: 326px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.selling-points .section-title {
  font-size: 28px;
  font-family: "Archivo Black", sans-serif;
  text-transform: uppercase;
  max-width: 370px;
}

.points {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: space-between;
}

.point {
  max-width: 300px;
  position: relative;
}

.point:nth-child(2) {
  margin-left: 50px;
}

.point .icon {
  position: absolute;
  left: -50px;
}

.point .title {
  font-size: 20px;
  font-weight: 700;
}

.point .description {
  font-size: 14px;
  color: #696969;
  line-height: 22px;
}
</style>