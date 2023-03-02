<template>
  <section class="world">
    <img src="@/assets/world.png" alt="world map" width="1000" height="539" />
  </section>
</template>

<style lang="scss" scoped>
.world {
  min-height: 100vh;
  background-color: $text-1;
  position: relative;
  img {
    position: absolute;
    bottom: 0;
    left: 15%;
  }
}
</style>
