<template>
  <div
    class="topbar bg-primary flex items-center font-18 text-white main-regular"
  >
    <div class="main-container">
      <span class="pl-5 lg:pl-20"> Welcome to Lumenac, SA </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Topbar",
};
</script>

<style scoped>
.topbar {
  height: 50px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
}
</style>
