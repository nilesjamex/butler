<template>
  <section class="question">
    <div class="question__text">
      <h2>Have a question?</h2>
      <p>
        Here are some of our most asked questions. If what you need is not here,
        do not hesitate to reach out.
      </p>
    </div>
    <div class="question__faq">
      <div
        class="item"
        v-for="item in faq"
        :key="item.id"
        :class="{ active: item.id === Id }"
      >
        <div>
          <h4>{{ item.question }}</h4>
          <span :class="{ active: item.id === Id }" @click="handleFaq(item.id)">
            <img src="@/assets/svg/plus.svg" alt="" />
          </span>
        </div>
        <p v-show="item.id === Id">
          {{ item.answer }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const Id = ref(0);
const faq = ref([
  {
    id: 1,
    question: "Alright, but what exactly do you do?",
    answer:
      "As a hospitality company, we work with you to ease you of your balablu you are currently encountering in the country, that’ depriving you off enjoyment in your day-to-day life.",
    showAnswer: false,
  },
  {
    id: 2,
    question: "does your food taste like trenches food?",
    answer:
      "As a hospitality company, we work with you to ease you of your balablu you are currently encountering in the country, that’ depriving you off enjoyment in your day-to-day life.",
    showAnswer: false,
  },
  {
    id: 3,
    question: "What’s your delivery process like?",
    answer:
      "As a hospitality company, we work with you to ease you of your balablu you are currently encountering in the country, that’ depriving you off enjoyment in your day-to-day life.",
    showAnswer: false,
  },
  {
    id: 4,
    question: "Why is your food so delicious?",
    answer:
      "As a hospitality company, we work with you to ease you of your balablu you are currently encountering in the country, that’ depriving you off enjoyment in your day-to-day life.",
    showAnswer: false,
  },
]);
const handleFaq = (identifier) => {
  if (Id.value === identifier) {
    Id.value = 0;
  } else {
    Id.value = identifier;
  }
};
</script>

<style lang="scss" scoped>
.question {
  min-height: 100vh;
  background-color: $text-1;
  padding: 3rem 7%;
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
      width: Min(606px, 100%);
    }
  }
  &__faq {
    margin-top: 3rem;
    .item {
      width: 100%;
      background-color: #ebe6dd;
      border-radius: Max(1.25rem, 20px);
      padding: 52px 60px;
      transition: all 0.5s ease-in-out;
      height: 155px;
      &.active {
        background-color: #d9d9d9;
        height: 230px;
        transition: all 0.5s ease-in-out;
      }
      & > div {
        @extend %flex-ac-jb;
        margin-bottom: 1rem;
        h4 {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 700;
          font-size: Max(2.188rem, 35px);
          line-height: 120%;
          color: $black;
        }
        span {
          width: 48px;
          height: 48px;
          background: #ffffff;
          border-radius: 24px;
          @extend %center;
          transition: all 0.5s ease-in-out;
          flex-shrink: 0;
          img {
            transition: all 0.5s ease-in-out;
          }
          &.active {
            background-color: $black;
            transition: all 0.5s ease-in-out;
            img {
              transform: rotate(45deg);
              fill: $white;
              filter: invert(1);
              transition: all 0.5s ease-in-out;
            }
          }
        }
      }
      p {
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 400;
        font-size: Max(1.125rem, 18px);
        line-height: 140%;
        color: $text-1;
        width: Min(750px, 100%);
      }
    }
  }
}
</style>
