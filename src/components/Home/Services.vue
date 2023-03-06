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
    img: require("@/assets/chart.png"),
    title: "Home Cleaning",
    desc: "High quality cleaning, on your schedule",
    colored: true,
  },
  {
    id: 2,
    img: require("@/assets/gem.png"),
    title: "Laundry Services",
    desc: "Professional Laundry Personalized",
    colored: false,
  },
  {
    id: 3,
    img: require("@/assets/gem.png"),
    title: "Food",
    desc: "Unique blend of exceptional food services.",
    colored: true,
  },
]);
</script>

<style lang="scss" scoped>
.service {
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
  }
  &__card {
    @extend %flex-ac-jb;
    gap: 1rem;
    margin-top: 7rem;
    .item {
      padding: 31px 20px;
      border: $border;
      border-radius: 1.25rem;
      width: Max(26.875rem, 430px);
      img {
        margin: 0 auto 4rem;
        @extend %center;
      }
      &__text {
        border-bottom: $border;
        margin-bottom: 1rem;
        padding: 0.5rem 0;
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
          font-size: Max(1.125rem, 18px);
          line-height: 120%;
          color: $white;
          margin: 0.5rem 0;
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
        transition: all 0.5s ease-in-out;
        &:hover {
          background: $text-3;
          color: $text-1;
          transition: all 0.5s ease-in-out;
        }
      }
    }
  }
}
</style>
