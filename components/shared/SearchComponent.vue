<template>
  <div class="site-search">
    <input type="text" class="site-search_input" placeholder="Search" />
    <img src="../../assets/icons/search.svg" alt="" />
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.site-search {
  border: solid 2px #efefef;
  border-radius: 60px;
  height: 50px;
  width: 300px;
  padding: 0 30px;
  display: flex;
  align-items: center;
}

.site-search_input {
  border: none;
  background: none;
  font-weight: 500;
  flex-grow: 1;
}

.site-search_input:focus {
  outline: none;
}

.site-search_input::placeholder {
  color: #c0c0c0;
}
</style>