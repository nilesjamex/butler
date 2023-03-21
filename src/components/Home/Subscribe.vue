<template>
  <section class="subscribe">
    <div class="subscribe__input">
      <div class="item">
        <p>
          Get updates about our products and our changelog. No spamming,
          promise!
        </p>
        <div class="subscribe__input__text">
          <input type="text" name="" id="" placeholder="Type your email..." />
          <span>
            <img src="@/assets/svg/send.svg" alt="" />
          </span>
        </div>
      </div>
    </div>
    <div class="subscribe__footer">
      <div class="socials">
        <img
          src="@/assets/svg/twitter.svg"
          alt="twitter icon"
          height="49.91"
          width="43.89"
        />
        <img
          src="@/assets/svg/linkedin.svg"
          alt="linkedin icon"
          height="49.91"
          width="47.91"
        />
        <img
          src="@/assets/svg/insta.svg"
          alt="instagram icon"
          height="49.91"
          width="49.91"
        />
        <img
          src="@/assets/svg/facebook.svg"
          alt="facebook icon"
          height="50"
          width="29.25"
        />
      </div>
      <div class="info">
        <dl>
          <dt>COMPANY</dt>
          <dd>About</dd>
          <dd>Pricing</dd>
          <dd>Services</dd>
          <dd>Contact</dd>
        </dl>
        <dl>
          <dt>RESOURCES</dt>
          <dd>Blog</dd>
          <dd>FAQ</dd>
          <dd>Brand Assets</dd>
        </dl>
        <dl>
          <dt>LINKS</dt>
          <dd>Careers</dd>
          <dd>Status</dd>
        </dl>
      </div>
    </div>
    <footer class="subscribe__foot">
      <h4>butler</h4>
      <div class="links">
        <p>Privacy</p>
        <p>Legal</p>
        <p>Terms and Condition</p>
      </div>
      <p>© Butler, All Rights Reserved. 2023.</p>
    </footer>
  </section>
</template>

<script></script>

<style lang="scss" scoped>
.subscribe {
  padding: 3rem 0 1.5rem;
  background-color: $text-2;
  overflow: hidden;
  &__input {
    border-bottom: $border;
    padding-bottom: 2.5rem;
    &__text {
      @extend %flex-ac;
      justify-content: space-between;
      width: 100%;
      @include respondMax("tablet2x") {
        border: $border;
        width: 90%;
      }
    }
    .item {
      background-color: $text-2;
      border: $border;
      width: fit-content;
      margin: 0 auto;
      flex-shrink: 0;
      @extend %flex-ac;
      //justify-content: space-between;
      @include respondMax("tablet2x") {
        flex-direction: column;
        border: none;
        gap: 1rem;
      }
      p {
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 400;
        font-size: Max(1rem, 16px);
        line-height: 112%;
        color: $white;
        width: Min(100%, 330px);
        padding: 0 1.5rem 0 0.5rem;
        border-right: $border;
        height: 70px;
        flex-shrink: 0;
        @extend %center;
        @include respondMax("tablet2x") {
          width: 95%;
          border-right: unset;
          height: auto;
          margin: 0 auto;
          text-align: center;
        }
      }
      input[type="text"] {
        //flex-shrink: 0;
        height: 100%;
        background-color: transparent;
        border: none;
        padding: 1rem;
        font-family: "Neurial Grotesk", sans-serif;
        font-style: normal;
        font-weight: 400;
        font-size: Max(1rem, 16px);
        line-height: 112%;
        color: $white;
        width: 100%;
        &::placeholder {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 400;
          font-size: Max(1rem, 16px);
          line-height: 112%;
          color: $white;
        }
      }
      span {
        @extend %center;
        width: 76px;
        height: 70px;
        background-color: #1f3138;
        flex-shrink: 0;
      }
    }
  }
  &__footer {
    margin-top: 1rem;
    padding: 1.5rem 7%;
    @include flex(flex-start, flex-start, row nowrap);
    gap: 10rem;
    @include respondMax("tablet2x") {
      gap: 2rem;
      flex-direction: column;
    }
    .socials {
      @extend %flex-ac;
      gap: 2rem;
      img {
        cursor: pointer;
      }
    }
    .info {
      @include flex(flex-start, flex-start, row wrap);
      gap: 8rem;
      @include respondMax("tablet2x") {
        gap: 2rem;
      }
      dl {
        dt {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 400;
          font-size: Max(1rem, 16px);
          line-height: 120%;
          color: #f2e2da;
        }
        dd {
          font-family: "Neurial Grotesk", sans-serif;
          font-style: normal;
          font-weight: 500;
          font-size: Max(1.125rem, 18px);
          line-height: 120%;
          color: $white;
          margin-top: 1.25rem;
          cursor: pointer;
        }
      }
    }
  }
  &__foot {
    padding: 0 7%;
    @include flex(space-between, flex-end, row wrap);
    gap: 1rem;
    h4 {
      font-family: "New Rocker", cursive;
      font-style: normal;
      font-weight: 400;
      font-size: 8rem;
      line-height: 80%;
      color: $white;
    }
    p {
      font-family: "Neurial Grotesk", sans-serif;
      font-style: normal;
      font-weight: 400;
      font-size: Max(1.125rem, 18px);
      line-height: 150%;
      color: $white;
    }
    .links {
      @extend %flex-ac;
      gap: 1.5rem;
      p {
        cursor: pointer;
      }
    }
  }
}
</style>
