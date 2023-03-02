<template>
  <section class="get">
    <h4>Get the Butler App.</h4>
    <div class="get__images">
      <img
        src="@/assets/appstore.png"
        alt="download on appstore"
        width="190"
        height="57"
      />
      <img
        src="@/assets/playstore.png"
        alt="download on appstore"
        width="190"
        height="57"
      />
    </div>
    <img
      src="@/assets/screen.png"
      alt="an iphone home screen"
      class="screen"
      width="511"
      height="500"
    />
  </section>
</template>

<style lang="scss" scoped>
.get {
  padding: 3rem 7% 0;
  background-color: $text-2;
  text-align: center;
  h4 {
    font-family: "Neurial Grotesk", sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 4rem;
    line-height: 135%;
    color: $white;
  }
  &__images {
    @extend %center;
    gap: 1.5rem;
    margin: 2rem 0 3.5rem;
  }
  .screen {
    margin: 0 auto;
  }
}
</style>
