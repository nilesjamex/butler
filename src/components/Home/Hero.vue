<template>
  <section class="hero">
    <div class="hero__heading">
      <h4>I believe in good design. Do you?</h4>
    </div>
    <div class="hero__button">
      <p>butler</p>
      <div class="button">
        <button
          v-for="item in button"
          :key="item.id"
          :class="{ active: item.id === 5 }"
        >
          {{ item.title }}
          <div v-html="item.icon" v-if="item.icon"></div>
        </button>
      </div>
    </div>
    <div class="hero__text">
      <p>Make your life easier than before without</p>
      <h6>Cleaning..</h6>
    </div>
    <p class="sub">
      We understand that life can be hectic, and that's why we're here to take
      care of the little things so you can focus on what's important.
    </p>
    <button class="started">GET BUTLERD 🚀</button>
    <div
      class="hero__cookie"
      :class="{ active: cookie }"
      v-if="$store.state.showCover"
    >
      <p>By using Butler, you agree with our cookie policy.</p>
      <img
        src="@/assets/svg/cancel.svg"
        alt="a cancel icon"
        height="30"
        width="30"
        @click="cookie = !cookie"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { useStore } from "vuex";
const store = useStore();
const button = ref([
  {
    id: 1,
    title: "About",
  },
  {
    id: 2,
    title: "Services",
    icon: `<svg width="9" height="15" viewBox="0 0 9 15" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M4.14645 14.8536C4.34171 15.0488 4.65829 15.0488 4.85355 14.8536L8.03553 11.6716C8.2308 11.4763 8.2308 11.1597 8.03553 10.9645C7.84027 10.7692 7.52369 10.7692 7.32843 10.9645L4.5 13.7929L1.67157 10.9645C1.47631 10.7692 1.15973 10.7692 0.964466 10.9645C0.769204 11.1597 0.769204 11.4763 0.964466 11.6716L4.14645 14.8536ZM4 0.5L4 14.5L5 14.5L5 0.5L4 0.5Z" fill="black"/>
</svg>
`,
  },
  {
    id: 3,
    title: "Resources",
    icon: `<svg width="9" height="15" viewBox="0 0 9 15" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M4.14645 14.8536C4.34171 15.0488 4.65829 15.0488 4.85355 14.8536L8.03553 11.6716C8.2308 11.4763 8.2308 11.1597 8.03553 10.9645C7.84027 10.7692 7.52369 10.7692 7.32843 10.9645L4.5 13.7929L1.67157 10.9645C1.47631 10.7692 1.15973 10.7692 0.964466 10.9645C0.769204 11.1597 0.769204 11.4763 0.964466 11.6716L4.14645 14.8536ZM4 0.5L4 14.5L5 14.5L5 0.5L4 0.5Z" fill="black"/>
</svg>
`,
  },
  {
    id: 4,
    title: "Contact",
  },
  {
    id: 5,
    title: "Get Started",
  },
]);
const cookie = ref(false);
setTimeout(() => {
  cookie.value = true;
}, 600);
if (window.sessionStorage.getItem("loaded") === null) {
  window.sessionStorage.setItem("loaded", true);
} else {
  store.state.showCover = false;
}
</script>

<style lang="scss" scoped>
.hero {
  background-color: #f2e2da;
  background-blend-mode: hue;
  height: 100vh;
  position: relative;
  &__heading {
    height: 42px;
    width: 100vw;
    background-color: $black;
    font-family: "Neurial Grotesk", sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 18px;
    line-height: 120%;
    color: #ffffff;
    @extend %center;
  }
  &__button {
    padding: 3rem 7%;
    @extend %flex-ac;
    gap: 10rem;
    .button {
      @extend %flex-ac;
      gap: 1rem;
      p {
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 500;
        font-size: Max(1.25rem, 20px);
        line-height: 120%;
        color: $text-1;
      }
      button {
        border-radius: 3.125rem;
        background-color: $white;
        padding: 1rem;
        width: auto;
        @extend %center;
        gap: 0.5rem;
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 500;
        font-size: Max(1.25rem, 20px);
        line-height: 120%;
        color: $black;
        &.active {
          background-color: $text-1;
          color: $white;
        }
      }
    }
  }
  &__text {
    width: Min(1099px, 100%);
    margin: 2rem auto;
    text-align: center;
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 700;
      font-size: 7rem;
      line-height: 120%;
      text-align: center;
      color: $black;
    }
    h6 {
      font-family: "Maglony";
      font-style: normal;
      font-weight: 600;
      font-size: 5rem;
      line-height: 150%;
      color: $text-2;
    }
  }
  p {
    &.sub {
      width: Min(530px, 100%);
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 400;
      font-size: Max(1.25rem, 20px);
      line-height: 120%;
      text-align: center;
      color: $text-1;
      margin: 0 auto;
    }
  }
  button {
    &.started {
      margin: 0 auto;
      width: auto;
      @extend %center;
      background-color: $text-1;
      border-radius: 3.125rem;
      margin-top: 2rem;
      padding: 15px 30px;
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 500;
      font-size: Max(1.25rem, 20px);
      line-height: 120%;
      color: $white;
    }
  }
  &__cookie {
    background: $white;
    border-radius: 10px;
    width: auto;
    max-width: 343px;
    padding: 1.5rem;
    @include flex(flex-start, flex-start, row nowrap);
    gap: 1.5rem;
    position: fixed;
    z-index: 3;
    bottom: 2%;
    right: 3%;
    transform: translateY(10vh);
    opacity: 0;
    transition: all 1s ease-in-out;
    &.active {
      opacity: 1;
      transition: all 1s ease-in-out;
      transform: translateY(0);
    }
    img {
      cursor: pointer;
    }
  }
}
</style>
