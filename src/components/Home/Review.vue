<template>
  <section class="review">
    <img
      src="@/assets/svg/in-love.svg"
      class="love"
      width="240"
      height="240"
      alt=""
    />
    <img
      src="@/assets/svg/excited.svg"
      class="excited"
      width="240"
      height="240"
      alt=""
    />
    <div class="review__text">
      <p>99% Customer Satisfaction.</p>
      <h4>They trust Butler. But why?</h4>
    </div>
    <button class="review__stars">
      <p>Google Ratings</p>
      <img src="@/assets/5-stars.svg" alt="google ratings" />
    </button>
    <div class="review__marquee">
      <div class="review__marquee__container">
        <div class="scroll">
          <div
            class="item"
            v-for="(item, index) in reviews"
            :key="index"
            :style="{ backgroundColor: item.bg }"
          >
            <img :src="item.icon" alt="user icon" width="69" height="69" />
            <div class="item__text">
              <div class="item__text__top">
                <h6 :style="{ color: item.textcolor }">{{ item.title }}</h6>
                <p :style="{ color: item.textcolor }">{{ item.role }}</p>
              </div>
              <h5 :style="{ color: item.textcolor2 }">
                {{ item.comment }}
              </h5>
            </div>
          </div>
          <div
            class="item"
            v-for="(item, index) in reviews"
            :key="index"
            :style="{ backgroundColor: item.bg }"
          >
            <img :src="item.icon" alt="user icon" width="69" height="69" />
            <div class="item__text">
              <div class="item__text__top">
                <h6 :style="{ color: item.textcolor }">{{ item.title }}</h6>
                <p :style="{ color: item.textcolor }">{{ item.role }}</p>
              </div>
              <h5 :style="{ color: item.textcolor2 }">
                {{ item.comment }}
              </h5>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="review__marquee">
      <div class="review__marquee__container two">
        <div class="scroll">
          <div
            class="item"
            v-for="(item, index) in reviews"
            :key="index"
            :style="{ backgroundColor: item.bg }"
          >
            <img :src="item.icon" alt="user icon" width="69" height="69" />
            <div class="item__text">
              <div class="item__text__top">
                <h6 :style="{ color: item.textcolor }">{{ item.title }}</h6>
                <p :style="{ color: item.textcolor }">{{ item.role }}</p>
              </div>
              <h5 :style="{ color: item.textcolor2 }">
                {{ item.comment }}
              </h5>
            </div>
          </div>
          <div
            class="item"
            v-for="(item, index) in reviews"
            :key="index"
            :style="{ backgroundColor: item.bg }"
          >
            <img :src="item.icon" alt="user icon" width="69" height="69" />
            <div class="item__text">
              <div class="item__text__top">
                <h6 :style="{ color: item.textcolor }">{{ item.title }}</h6>
                <p :style="{ color: item.textcolor }">{{ item.role }}</p>
              </div>
              <h5 :style="{ color: item.textcolor2 }">
                {{ item.comment }}
              </h5>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const reviews: {
  // eslint-disable-next-line @typescript-eslint/no-explicit-any
  icon: any;
  title: string;
  role: string;
  comment: string;
  bg: string;
  textcolor: string;
  textcolor2: string;
}[] = [
  {
    icon: require("@/assets/user.png"),
    title: "Moses Adebayo",
    role: "Creative Director",
    comment:
      "Lorem ipsum dolor sit amet consectetur. Aenean nibh gravida convallis cursus varius a. Amet sagittis at diam interdum.",
    bg: "#1F3138",
    textcolor: "#D6EEE9",
    textcolor2: "#FFFFFF",
  },
  {
    icon: require("@/assets/user.png"),
    title: "Niles James",
    role: "Frontend Developer",
    comment:
      "Lorem ipsum dolor sit amet consectetur. Aenean nibh gravida convallis cursus varius a. Amet sagittis at diam interdum. ",
    bg: "#51DA7F",
    textcolor: "#1F3138",
    textcolor2: "#1F3138",
  },
  {
    icon: require("@/assets/user.png"),
    title: "Moses Adebayo",
    role: "Creative Director",
    comment:
      "Lorem ipsum dolor sit amet consectetur. Aenean nibh gravida convallis cursus varius a. Amet sagittis at diam interdum.",
    bg: "#1F3138",
    textcolor: "#D6EEE9",
    textcolor2: "#FFFFFF",
  },
  {
    icon: require("@/assets/user.png"),
    title: "Niles James",
    role: "Frontend Developer",
    comment:
      "Lorem ipsum dolor sit amet consectetur. Aenean nibh gravida convallis cursus varius a. Amet sagittis at diam interdum. ",
    bg: "#8E3AE2",
    textcolor: "#D6EEE9",
    textcolor2: "#FFFFFF",
  },
  {
    icon: require("@/assets/user.png"),
    title: "Moses Adebayo",
    role: "Creative Director",
    comment:
      "Lorem ipsum dolor sit amet consectetur. Aenean nibh gravida convallis cursus varius a. Amet sagittis at diam interdum.",
    bg: "#071012",
    textcolor: "#D6EEE9",
    textcolor2: "#FFFFFF",
  },
];
</script>

<style lang="scss" scoped>
.review {
  --gap-space: 1.5rem;
  --space-sm: 1rem;
  --top-space: 0.5rem;
  min-height: 100vh;
  background-color: #f2e2da;
  background-blend-mode: hue;
  background-image: url(@/assets/hue2.png);
  background-size: cover;
  background-repeat: no-repeat;
  padding: 3rem 0;
  position: relative;
  @include respondMax("tablet2x") {
    min-height: unset;
  }
  @keyframes infinityScroll {
    100% {
      transform: translateX(-50%);
    }
  }
  @keyframes infinityScroll2 {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  @keyframes love {
    0% {
      transform: translateX(0);
    }
    50% {
      transform: translateX(30px);
    }
    100% {
      transform: translateX(0);
    }
  }
  @keyframes excited {
    0% {
      transform: translateX(0);
    }
    50% {
      transform: translateX(-30px);
    }
    100% {
      transform: translateX(0);
    }
  }
  .love {
    position: absolute;
    right: 5%;
    top: 1%;
    animation-name: love;
    animation-timing-function: ease;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    @include respondMax("tablet2x") {
      display: none;
    }
  }
  .excited {
    position: absolute;
    right: 14%;
    top: 17%;
    animation-name: excited;
    animation-timing-function: ease;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    @include respondMax("tablet2x") {
      display: none;
    }
  }
  &__text {
    padding: 0 7%;
    margin-bottom: 3rem;
    @include respondMax("tablet2x") {
      text-align: center;
    }
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 400;
      font-size: Max(1.25rem, 18px);
      line-height: 125%;
      color: $black;
    }
    h4 {
      width: Min(509px, 100%);
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: 4rem;
      line-height: 130%;
      color: $black;
      @include respondMax("tablet2x") {
        margin: 0 auto;
      }
      @include respondMax("mobile2x") {
        p {
          font-size: 1rem;
        }
        h4 {
          font-size: 2rem;
        }
      }
    }
  }
  &__stars {
    width: auto;
    margin: 2rem auto 4rem auto;
    @extend %center;
    padding: 10px;
    border: 1px solid #1f3138;
    border-radius: Max(3.125rem, 50px);
    background-color: transparent;
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: Max(1.25rem, 18px);
      line-height: 125%;
      color: $text-1;
    }
  }
  &__marquee {
    background-color: transparent;
    width: 100%;
    max-width: 100vw;
    overflow: hidden;
    @extend %flex-ac;
    gap: var(--gap-space);
    margin: var(--top-space) 0;
    &__container {
      flex-shrink: 0;
      gap: var(--gap-space);
      padding-right: var(--gap-space);
      animation: infinityScroll 17s linear 0s infinite forwards;
      // animation-delay: 4s;
      @extend %flex-ac;
      width: max-content;
      max-width: unset;
      overflow: hidden;
      &.two {
        animation: infinityScroll2 22s linear 0s infinite reverse;
      }
      &:hover {
        animation-play-state: paused;
      }
      .scroll {
        @extend %flex-ac;
        gap: var(--gap-space);
        max-width: unset;
        .item {
          background-color: $text-1;
          border-radius: 1.25rem;
          padding: 30px 40px;
          width: 573px;
          height: 185px;
          @include flex(flex-start, flex-start, row nowrap);
          gap: var(--space-sm);
          &__text {
            &__top {
              margin-bottom: 0.6rem;
              h6 {
                font-family: "Neurial Grotesk", sans-serif;
                font-style: normal;
                font-weight: 500;
                font-size: Max(1.125rem, 18px);
                line-height: 125%;
                color: #d6eee9;
                margin-bottom: 0.15rem;
              }
              p {
                font-family: "Neurial Grotesk", sans-serif;
                font-style: normal;
                font-weight: 500;
                font-size: Max(1.125rem, 18px);
                line-height: 125%;
                color: #d6eee9;
              }
            }
            h5 {
              font-family: "Neurial Grotesk", sans-serif;
              font-style: italic;
              font-weight: 500;
              font-size: Max(1.125rem, 18px);
              line-height: 125%;
              color: $white;
            }
          }
        }
      }
    }
  }
}
</style>
