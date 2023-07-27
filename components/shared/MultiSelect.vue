<template>
  <ul class="multi-select">
    <li class="option" :class="{ selected: all }" @click="reset">
      {{ allText }}
    </li>
    <li
      v-for="key in optionsToArray"
      :key="key + 5"
      class="option"
      :class="{ selected: options[key] }"
      @click="toggle(key)"
    >
      {{ key }}
    </li>
  </ul>
</template>

<script>
export default {
  emits: ["options"],
  data() {
    return {
      useAll: true,
      allText: "all categories",
      options: {
        art: false,
        celebrities: false,
        gaming: false,
        sports: false,
        music: false,
        crypto: false,
      },
    };
  },
  methods: {
    toggle(key) {
      this.options[key] = !this.options[key];
    },
    reset() {
      this.optionsToArray.forEach((option) => (this.options[option] = false));
    },
  },
  watch: {
    options: {
      handler: function (value) {
        this.$emit("options", value);
        console.log(value);
      },
      deep: true,
    },
  },
  computed: {
    optionsToArray() {
      return Object.keys(this.options);
    },
    all() {
      return Object.values(this.options).reduce((allFalse, currOption) => {
        return currOption === false && allFalse;
      }, true);
    },
  },
};
</script>

<style scoped>
.multi-select {
  display: flex;
  list-style: none;
  padding: 0;
  @apply gap-[20px];
}
.option {
  @apply capitalize text-[14px] px-[20px] h-[28px] flex items-center justify-center bg-[rgba(220,220,220,0.2)] rounded-full cursor-pointer font-[500] transition-colors;
}

.selected {
  @apply bg-[#3D00B7] text-white;
}
</style>