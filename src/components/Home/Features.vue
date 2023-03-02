<template>
  <section class="features">
    <h4>Top features you should expect, with little to zero charges..</h4>
    <div class="features__content">
      <div class="pricing">
        <p>Our pricing strategy is transparent.</p>
        <p>Our pricing strategy is transparent.</p>
        <p>Our pricing strategy is transparent.</p>
        <p>Our pricing strategy is transparent.</p>
        <p>Our pricing strategy is transparent.</p>
      </div>
      <div class="grid">
        <ul>
          <li style="--x1: 2; --x2: 6; --y1: 1; --y2: 4">
            <img src="https://picsum.photos/600/600?random=1" alt="" />
          </li>
          <li style="--x1: 6; --x2: 8; --y1: 2; --y2: 4">
            <img src="https://picsum.photos/600/600?random=2" alt="" />
          </li>
          <li style="--x1: 1; --x2: 4; --y1: 4; --y2: 7">
            <img src="https://picsum.photos/600/600?random=3" alt="" />
          </li>
          <li style="--x1: 4; --x2: 7; --y1: 4; --y2: 7">
            <img src="https://picsum.photos/600/600?random=4" alt="" />
          </li>
          <li style="--x1: 7; --x2: 9; --y1: 4; --y2: 6">
            <img src="https://picsum.photos/600/600?random=5" alt="" />
          </li>
          <li style="--x1: 2; --x2: 4; --y1: 7; --y2: 9">
            <img src="https://picsum.photos/600/600?random=7" alt="" />
          </li>
          <li style="--x1: 4; --x2: 7; --y1: 7; --y2: 10">
            <img src="https://picsum.photos/600/600?random=8" alt="" />
          </li>
          <li style="--x1: 7; --x2: 10; --y1: 6; --y2: 9">
            <img src="https://picsum.photos/600/600?random=9" alt="" />
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script></script>

<style lang="scss" scoped>
.features {
  height: 100vh;
  background-color: $text-2;
  padding: 3rem 7%;
  h4 {
    font-family: "Neurial Grotesk", sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 4rem;
    line-height: 130%;
    width: Min(940px, 100%);
    color: $white;
  }
  &__content {
    @extend %flex-ac;
    .grid {
      display: grid;
      ul {
        --big-tile-size: 50vmin;
        --scale: 0.4;
        --rotation: 270deg;
        --tile-size: calc(var(--big-tile-size) / 3);
        list-style-type: none;
        padding: 0;
        margin: 0;
        display: grid;
        gap: 1vmin;
        grid-template: repeat(9, var(--tile-size)) / repeat(9, var(--tile-size));
        transform: translate(-50%, -50%) scale(var(--scale));
      }
      li {
        grid-column: var(--x1, auto) / var(--x2, auto);
        grid-row: var(--y1, auto) / var(--y2, auto);
      }

      li {
        border-radius: var(--radius-2);
        overflow: hidden;
      }
    }
  }
}
</style>
