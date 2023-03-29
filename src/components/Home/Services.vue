<template>
  <section class="service">
    <div class="service__text">
      <h2>Our Services</h2>
      <p>We built everything with you in mind.</p>
    </div>
    <div class="service__card">
      <div class="item" v-for="item in services" :key="item.id">
        <img :src="item.img" alt="" height="226" width="206" />
        <div class="item__text">
          <h4>{{ item.title }}</h4>
          <p>{{ item.desc }}</p>
        </div>
        <button :class="{ active: item.colored }">Learn More</button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const services = ref([
  {
    id: 1,
    img: require("@/assets/Glasses.png"),
    title: "Home Cleaning",
    desc: "High quality cleaning, on your schedule",
    colored: true,
  },
  {
    id: 2,
    img: require("@/assets/bars.png"),
    title: "Laundry Services",
    desc: "Professional Laundry Personalized",
    colored: false,
  },
  {
    id: 3,
    img: require("@/assets/Soup.png"),
    title: "Food",
    desc: "Unique blend of exceptional food services.",
    colored: true,
  },
]);
</script>

<style lang="scss" scoped>
.service {
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
  min-height: 100vh;
  background-color: $text-1;
  padding: 4rem 7%;
  &__text {
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
    @include respondMax("mobile2x") {
      h2 {
        font-size: 2rem;
      }
      p {
        font-size: 1.5rem;
      }
    }
  }
  &__card {
    @extend %flex-ac-jb;
    gap: 1rem;
    margin-top: 7rem;
    @media screen and (max-width: 1300px) {
      flex-wrap: wrap;
    }
    .item {
      padding: 31px 20px;
      border: $border;
      border-radius: 1.25rem;
      width: Max(26.875rem, 430px);
      max-height: 550px;
      height: 550px;
      @media screen and (max-width: 1300px) {
        flex-grow: 1;
        text-align: left;
        max-height: 490px;
      }
      img {
        margin: 0 auto 4rem;
        @extend %center;
        animation-name: bounce;
        animation-timing-function: ease;
        animation-duration: 3s;
        animation-iteration-count: infinite;
      }
      &__text {
        border-bottom: $border;
        margin-bottom: 1rem;
        padding: 0.2rem 0;
        h4 {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 500;
          font-size: Max(2.375rem, 20px);
          line-height: 150%;
          color: $white;
        }
        p {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 400;
          font-size: Max(1.125rem, 16px);
          line-height: 120%;
          color: $white;
          margin: 0.2rem 0;
        }
      }
      button {
        width: auto;
        padding: 10px 20px;
        background: transparent;
        border-radius: 3.125rem;
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 500;
        font-size: Max(1.125rem, 18px);
        line-height: 120%;
        border: $border;
        color: $text-3;
        margin-top: 0.65rem;
        transition: all 0.2s ease-in-out;
        &:hover {
          background: $text-3;
          color: $text-1;
          transition: all 0.2s ease-in-out;
        }
        @media screen and (max-width: 1300px) {
          height: auto;
        }
      }
    }
  }
}
</style>
