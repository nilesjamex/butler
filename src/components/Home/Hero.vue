<template>
  <section class="hero">
    <img
      src="@/assets/svg/balloon.svg"
      class="ballon"
      width="240"
      height="240"
      alt=""
    />
    <img
      src="@/assets/svg/bee.svg"
      width="100"
      class="bee"
      height="83"
      alt=""
    />
    <img
      src="@/assets/svg/frog.svg"
      width="203"
      class="frog"
      height="166"
      alt=""
    />
    <img
      src="@/assets/svg/star.svg"
      width="108"
      class="star"
      height="109"
      alt=""
    />
    <div class="hero__heading">
      <h4>I believe in good design. Do you?</h4>
    </div>
    <div class="hero__button">
      <p>butler</p>
      <div class="button" :class="{ button__active: active }">
        <button
          @click="active = !active"
          v-for="item in button"
          :key="item.id"
          :class="{ active: item.id === 5 }"
        >
          {{ item.title }}
          <div v-html="item.icon" v-if="item.icon"></div>
        </button>
      </div>
      <div class="toggle" @click="active = !active">
        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
      </div>
    </div>
    <div class="hero__text">
      <p>Make your life easier than before without</p>
      <!-- <div class="hero__text__sub">
        <div>
          <h6>Cleaning..</h6>
          <h6>Food</h6>
          <h6>Love</h6>
        </div>
      </div> -->
      <div class="demo"></div>
      <!-- <div class="pushcontain">
        <div class="push">
          <span :class="count === 1 ? `active` : ``">L</span
          ><span :class="count === 1 ? `active` : ``">A</span
          ><span :class="count === 1 ? `active` : ``">U</span
          ><span :class="count === 1 ? `active` : ``">N</span
          ><span :class="count === 1 ? `active` : ``">D</span
          ><span :class="count === 1 ? `active` : ``">R</span
          ><span :class="count === 1 ? `active` : ``">Y</span>
        </div>
        <div class="push">
          <span :class="count === 2 ? `active` : ``">F</span
          ><span :class="count === 2 ? `active` : ``">O</span
          ><span :class="count === 2 ? `active` : ``">O</span
          ><span :class="count === 2 ? `active` : ``">D</span>
        </div>
        <div class="push">
          <span :class="count === 3 ? `active` : ``">C</span
          ><span :class="count === 3 ? `active` : ``">L</span
          ><span :class="count === 3 ? `active` : ``">E</span
          ><span :class="count === 3 ? `active` : ``">A</span>
          <span :class="count === 3 ? `active` : ``">N</span
          ><span :class="count === 3 ? `active` : ``">I</span
          ><span :class="count === 3 ? `active` : ``">N</span
          ><span :class="count === 3 ? `active` : ``">G</span>
        </div>
      </div> -->
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
import { onMounted, ref } from "vue";
import { useStore } from "vuex";
import SplitTextJS from "split-text-js";
import { gsap, Linear } from "gsap";
const store = useStore();
const active = ref(false);
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
const show = ref(true);
const count = ref(1);
setInterval(() => {
  if (count.value === 3) {
    count.value = 1;
  } else {
    count.value++;
  }
}, 3000);
const titles = gsap.utils.toArray("h6");
const tl = gsap.timeline();
// iterate over each titles
//console.log(titles);
titles.forEach((title) => {
  //console.log(title);
  const splitTitle = new SplitTextJS(title);
  //console.log(splitTitle);
  // tl.from(
  //   splitTitle.chars,
  //   {
  //     opacity: 0,
  //     y: 80,
  //     rotateX: -90,
  //     stagger: 0.02,
  //     ease: Linear.easeNone,
  //     repeat: -1,
  //   },
  //   "<"
  // ).to(
  //   splitTitle.chars,
  //   {
  //     opacity: 0,
  //     y: -80,
  //     rotateX: 90,
  //     stagger: 0.02,
  //     ease: Linear.easeNone,
  //     repeat: -1,
  //   },
  //   "<1"
  // );
});
onMounted(() => {
  let phrases = ["Laundry", "Cleaning", "Food"];
  let demo = document.querySelector(".demo");
  console.log(demo);
  let animation = gsap.timeline({ repeat: -1, repeatDelay: 0.5 });
  const createLayers = () => {
    phrases.forEach((phrase) => {
      let layer = document.createElement("h6");
      layer.innerHTML = phrase;
      demo.appendChild(layer);
    });
  };
  const animateText = () => {
    let layers = document.querySelectorAll(".demo h6");
    layers.forEach(function (element) {
      animation.fromTo(
        element,
        { opacity: 0, y: 30 },
        {
          opacity: 1,
          duration: 1,
          y: 0,
          repeat: 1,
          yoyo: true,
          yoyoEase: true,
          repeatDelay: 0.3,
        }
      );
    });
    gsap.set(".demo", { visibility: "visible" });
  };
  createLayers();
  animateText();
});
</script>

<style lang="scss" scoped>
.hero {
  background-color: #f2e2da;
  background-blend-mode: hue;
  background-image: url(@/assets/hue2.png);
  background-size: cover;
  background-repeat: no-repeat;
  min-height: 100vh;
  position: relative;
  padding-bottom: 3rem;
  @media screen and (max-width: 1300px) {
    min-height: 40vh;
  }
  @keyframes bounce {
    0% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-35px);
    }
    100% {
      transform: translateY(0);
    }
  }
  @keyframes ballonnBounce {
    0% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-5px);
    }
    100% {
      transform: translateY(0);
    }
  }
  @keyframes bee {
    0% {
      transform: rotate(0);
    }
    50% {
      transform: rotate(-50deg);
    }
    100% {
      transform: rotate(0);
    }
  }
  @keyframes frog {
    0% {
      transform: rotate(180deg);
    }
    50% {
      transform: rotate(-180deg);
    }
    100% {
      transform: rotate(180deg);
    }
  }
  .ballon {
    position: absolute;
    right: 2%;
    top: 15%;
    animation-name: ballonnBounce;
    animation-timing-function: ease;
    animation-duration: 2s;
    animation-iteration-count: infinite;
    z-index: 1;
    @media screen and (max-width: 1300px) {
      top: 10%;
      width: 20%;
      height: 20%;
    }
  }
  .star {
    position: absolute;
    left: 5%;
    top: 54%;
    animation-name: bounce;
    animation-timing-function: ease;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    @media screen and (max-width: 1300px) {
      top: 60%;
      width: 20%;
      height: 20%;
    }
  }
  .bee {
    position: absolute;
    left: 15%;
    bottom: 7%;
    animation-name: bee;
    animation-timing-function: ease;
    animation-duration: 3s;
    animation-iteration-count: infinite;
  }
  .frog {
    position: absolute;
    right: 5%;
    bottom: 6%;
    animation-name: frog;
    animation-timing-function: ease;
    animation-duration: 6s;
    animation-iteration-count: infinite;
    @media screen and (max-width: 1300px) {
      top: 85%;
      width: 30%;
      height: 30%;
    }
  }
  &__heading {
    height: 42px;
    width: 100vw;
    background-color: $black;
    font-family: "Neurial Grotesk", sans-serif;
    font-style: bold;
    font-weight: 500;
    font-size: 18px;
    line-height: 120%;
    color: #ffffff;
    @extend %center;
    @media screen and (max-width: 1300px) {
      height: 30px;
      font-size: 1.1rem;
    }
  }
  .demo {
    //display: none;
  }
  &__button {
    padding: 3rem 7%;
    @extend %flex-ac-jb;
    .toggle {
      display: none;
      @include respondMax("tablet2x") {
        display: block;
        z-index: 5;
      }
      .box {
        width: 25px;
        height: 1.5px;
        background-color: $text-1;
        margin: 0.25rem 0;
      }
    }
    .button {
      @extend %flex-ac;
      gap: 1rem;
      @include respondMax("tablet2x") {
        position: fixed;
        display: flex;
        flex-direction: column;
        gap: 1.5rem;
        top: 8vh;
        bottom: 0;
        right: 0;
        order: 1;
        transition: all 0.2s ease-out;
        overflow: hidden;
        z-index: 4;
        padding: 5% 1.5rem 3%;
        height: 100%;
        width: 100%;
        background-color: #f2e2da;
        background-blend-mode: hue;
        background-image: url(@/assets/hue2.png);
        background-size: cover;
        background-repeat: no-repeat;
        transform: translateX(100%);
        &__active {
          transform: translateX(0%);
        }
      }
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
        font-size: Max(0.9rem, 15px);
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
    .demo {
      font-family: "Maglony";
      font-style: normal;
      font-weight: 600;
      font-size: 5rem;
      line-height: 0;
      color: $text-2;
      position: relative;
      z-index: 2;
      //display: none;
      h6 {
        color: $text-2;
      }
    }
    .push {
      font-family: "Maglony";
      font-style: normal;
      font-weight: 600;
      font-size: 5rem;
      line-height: 0;
      margin: 0;
      color: $text-2;
      span {
        display: inline-block;
        &:nth-child(1) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1s ease-in;
        }
        &:nth-child(2) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.1s ease-in;
        }
        &:nth-child(3) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.2s ease-in;
        }
        &:nth-child(4) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.3s ease-in;
        }
        &:nth-child(5) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.4s ease-in;
        }
        &:nth-child(6) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.5s ease-in;
        }
        &:nth-child(7) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.6s ease-in;
        }
        &:nth-child(8) {
          transform: translateY(15px);
          opacity: 0;
          transition: all 1.7s ease-in;
        }
        &.active {
          &:nth-child(1) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1s ease-in;
          }
          &:nth-child(2) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.1s ease-in;
          }
          &:nth-child(3) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.2s ease-in;
          }
          &:nth-child(4) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.3s ease-in;
          }
          &:nth-child(5) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.4s ease-in;
          }
          &:nth-child(6) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.5s ease-in;
          }
          &:nth-child(7) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.6s ease-in;
          }
          &:nth-child(8) {
            transform: translateY(0);
            opacity: 1;
            transition: all 1.7s ease-in;
          }
        }
        &.not {
          &:nth-child(1) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1s ease-out;
          }
          &:nth-child(2) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.1s ease-out;
          }
          &:nth-child(3) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.2s ease-out;
          }
          &:nth-child(4) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.3s ease-out;
          }
          &:nth-child(5) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.4s ease-out;
          }
          &:nth-child(6) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.5s ease-out;
          }
          &:nth-child(7) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.6s ease-out;
          }
          &:nth-child(8) {
            transform: translateY(-15px);
            opacity: 0;
            transition: all 1.7s ease-out;
          }
        }
      }
    }
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 700;
      font-size: 7rem;
      line-height: 120%;
      text-align: center;
      color: $black;
      margin-bottom: 3rem;
      position: relative;
      z-index: 2;
      @media screen and (max-width: 850px) {
        font-size: 4rem;
      }
      @include respondMax("mobile2x") {
        font-size: 4rem;
        margin: 8%;
        font-weight: 700;
      }
    }
    h6 {
      font-family: "Maglony";
      font-style: normal;
      font-weight: 600;
      font-size: 5rem;
      line-height: 150%;
      margin: 0;
      color: $text-2;
      position: relative;
      z-index: 2;
    }
  }
  p {
    &.sub {
      width: Min(530px, 90%);
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 400;
      font-size: Max(1.25rem, 20px);
      line-height: 120%;
      text-align: center;
      color: $text-1;
      margin: 4rem auto;
      position: relative;
      z-index: 2;
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
      // font-size: Max(1.25rem, 20px);
      line-height: 120%;
      color: $white;
      &:hover {
        background-color: #275f0b;
        color: $white;
        transition: background-color 0.2s ease-in-out;
      }
      @media screen and (max-width: 1300px) {
        padding: 30px 30px;
        margin-bottom: 200px;
      }
    }
  }
  &__cookie {
    background: $white;
    border-radius: 10px;
    width: auto;
    max-width: 250px;
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
