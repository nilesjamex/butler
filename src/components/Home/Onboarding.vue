<template>
  <section class="onboard">
    <div class="onboard__text">
      <h2>Onboarding is the easiest.</h2>
      <p>
        Start automating your tasks and house chores with our 3 simple step
        process.
      </p>
    </div>
    <div class="onboard__content">
      <img
        src="@/assets/onboard.png"
        alt="get started"
        width="634"
        height="520"
      />
      <div class="item">
        <h4>How it Works.</h4>
        <ul>
          <li v-for="item in list" :key="item.id">
            <div class="item__numbering">
              <span> {{ item.id }}</span>
              <h6>{{ item.titel }}</h6>
            </div>
            <p>{{ item.desc }}</p>
          </li>
        </ul>
      </div>
    </div>
    <div class="onboard__marquee">
      <div class="onboard__marquee__container">
        <div>
          <span v-for="item in marquee" :key="item.id">
            <span></span>
            {{ item.titel }}
          </span>
        </div>
        <div>
          <span v-for="item in marquee" :key="item.id">
            <span></span>
            {{ item.titel }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const list = ref([
  {
    id: 1,
    titel: "Download the App and create your profile.",
    desc: "Lorem ipsum dolor sit amet consectetur. Natoquenec lacinia sed orci. Adipiscing dolor proin nibh ipsumrisus. Elit in commodo nunc metus pulvinar mattis.",
  },
  {
    id: 2,
    titel: "Subscribe to a service.",
    desc: "Lorem ipsum dolor sit amet consectetur. Natoquenec lacinia sed orci. Adipiscing dolor proin nibh ipsumrisus. Elit in commodo nunc metus pulvinar mattis.",
  },
  {
    id: 3,
    titel: "Get your service.",
    desc: "Lorem ipsum dolor sit amet consectetur. Natoquenec lacinia sed orci. Adipiscing dolor proin nibh ipsumrisus. Elit in commodo nunc metus pulvinar mattis.",
  },
]);
const marquee = ref([
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
  {
    id: 1,
    titel: "Butler is the best i’ve used!",
  },
]);
</script>

<style lang="scss" scoped>
.onboard {
  height: 100vh;
  background-color: $text-1;
  position: relative;
  padding: 3rem 0 0;
  --gap-space: 1.5rem;
  --space-sm: 1rem;
  --top-space: 0.5rem;
  @keyframes infinityScroll {
    100% {
      transform: translateX(-50%);
    }
  }
  &__text {
    padding: 0 7%;
    h2 {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 700;
      font-size: 4rem;
      line-height: 120%;
      color: $white;
      margin-bottom: 0.3rem;
    }
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: Max(1.125rem, 18px);
      line-height: 120%;
      color: $white;
    }
  }
  &__content {
    margin-top: 3rem;
    @extend %flex-ac;
    gap: 2rem;
    padding: 0 7%;
    .item {
      background-color: $white;
      background: linear-gradient(146.61deg, #ffffff 11.76%, #ffffff 89.59%);
      box-shadow: 5px 15px 22px rgba(0, 0, 0, 0.05);
      border-radius: 20px;
      min-width: 591px;
      width: 100%;
      height: 520px;
      padding: 40px 30px;
      h4 {
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 500;
        font-size: Max(2.375rem, 20px);
        line-height: 150%;
        color: $black;
        margin-bottom: 1rem;
      }
      &__numbering {
        @extend %flex-ac;
        gap: 1rem;
        margin-bottom: 1rem;
        span {
          background-color: $text-1;
          height: 21px;
          width: 21px;
          border-radius: 100%;
          @extend %center;
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 500;
          font-size: Max(1rem, 16px);
          line-height: 110%;
          color: $white;
        }
        h6 {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 700;
          font-size: Max(1.125rem, 18px);
          line-height: 120%;
          color: $black;
        }
      }
      ul {
        li {
          &:not(:last-child) {
            margin-bottom: 2.5rem;
          }
          p {
            font-family: "Neurial Grotesk", sans-serif;
            font-style: normal;
            font-weight: 500;
            font-size: Max(0.875rem, 14px);
            line-height: 115%;
            color: $black;
            width: Min(100%, 351px);
          }
        }
      }
    }
  }
  &__marquee {
    background: #f9d895;
    height: Max(4.563rem, 73px);
    width: 100%;
    max-width: 100vw;
    overflow: hidden;
    @extend %flex-ac;
    gap: var(--gap-space);
    position: absolute;
    bottom: 0;
    &__container {
      flex-shrink: 0;
      gap: var(--gap-space);
      padding-right: var(--gap-space);
      animation: infinityScroll 18s linear 0s infinite forwards;
      // animation-delay: 4s;
      @extend %flex-ac;
      width: max-content;
      max-width: unset;
      overflow: hidden;
      &:hover {
        animation-play-state: paused;
      }
      & > div {
        @extend %flex-ac;
        gap: var(--gap-space);
        max-width: unset;
        span {
          @extend %flex-ac;
          gap: var(--gap-space);
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 700;
          font-size: Max(1.25rem, 18px);
          line-height: 120%;
          color: $text-1;
          span {
            background-color: $text-1;
            height: 7px;
            width: 7px;
            border-radius: 100%;
            margin-bottom: unset;
          }
        }
      }
    }
  }
}
</style>
