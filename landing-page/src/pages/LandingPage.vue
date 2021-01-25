<template>
  <div>
    <div class="container" :class="$mq" id="hero">
      <div class="inner-content" :class="$mq">
        <div :class="$mq">
          <h1 :class="$mq">
            The worlds most comfortable and ethical running shoe
          </h1>
          <p :class="$mq">
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur
            irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim
            pariatur irure.
          </p>
          <button @click="openModal" class="waitlist-button">
            Join the waitlist
          </button>
        </div>
      </div>
    </div>
    <div class="container" :class="$mq">
      <div class="inner-content" :class="$mq">
        <img src="../assets/runner-second.jpg" />
        <div class="text-container" :class="$mq">
          <h4>A shoe for the future</h4>
          <h2>Comfortably concious</h2>
          <p>
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur
            irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim
            pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna
            fugiat enim pariatur irure.
          </p>
        </div>
      </div>
    </div>
    <div class="container" id="card" :class="$mq">
      <div class="inner-content" :class="$mq">
        <h2>Why people love this shoe</h2>
        <div class="holder" :class="$mq">
          <Card v-for="(card, index) in cards" :key="index" :card="card" />
        </div>
      </div>
    </div>
    <div class="container" :class="$mq">
      <div class="inner-content" :class="$mq">
        <div class="text-container">
          <h4>A shoe for the future</h4>
          <h2>Comfortably concious</h2>
          <p>
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur
            irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim
            pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna
            fugiat enim pariatur irure.
          </p>
        </div>
        <img src="../assets/runner-fourth.jpg" />
      </div>
    </div>
    <div class="container" id="final" :class="$mq">
      <div class="inner-content" :class="$mq">
        <div class="image">
          <div>
            <h2 :class="$mq">Ready to change the world one step at a time?</h2>
            <p :class="$mq">
              Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim
              pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna
              fugiat enim pariatur irure.
            </p>
            <button @click="openModal" class="waitlist-button">
              Join the waitlist
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "../components/Card";

export default {
  components: {
    Card,
  },
  data() {
    return {
      cards: [
        {
          title: "100% Recylced Materials",
          icon: "icon1.svg",
          text:
            "Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.",
        },
        {
          title: "Mega Boost Technology",
          icon: "icon2.svg",
          text:
            "Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.",
        },
        {
          title: "Ethically Sourced Labour",
          icon: "icon3.svg",
          text:
            "Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure. Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.",
        },
      ],
    };
  },
  methods: {
    openModal() {
      this.$emit("open");
    },
  },
};
</script>

<style lang="scss" scoped>
$green: #a0c633;
$title-font: "Montserrat", sans-serif;

.container {
  height: 100vh;
  background: #fafafa;
  display: flex;
  justify-content: center;
  align-items: center;
  &.mobile {
    min-height: 100vh;
    height: auto;
  }
  .inner-content {
    max-width: 1440px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    &.mobile {
      flex-direction: column;
    }
  }
  p {
    color: #4b514b;
    line-height: 145%;
  }
  &#hero {
    background-image: url("../assets/runner-hero.jpg");
    background-position: center;
    background-size: cover;
    &.mobile {
      background-position: inherit;
    }
    .inner-content {
      justify-content: flex-start;
      &.mobile {
        padding: 10px;
      }
      div {
        display: flex;
        flex-direction: column;
        width: 70%;
        &.mobile {
          width: 100%;
        }
        h1 {
          color: #fff;
          font-size: 65px;
          letter-spacing: 2px;
          font-weight: 700;
          font-family: $title-font;
          margin-bottom: 0px;
          &.mobile {
            font-size: 30px;
          }
        }
        p {
          font-size: 20px;
          letter-spacing: 1px;
          color: #fff;
          line-height: 24px;
          &.mobile {
            font-size: 15px;
          }
        }
      }
    }
  }
  &#card {
    flex-direction: column;
    background-color: #fff;
    .inner-content {
      flex-direction: column;
    }
    .holder {
      display: flex;
      justify-content: space-evenly;
      width: 100%;
      &.mobile {
        flex-direction: column;
      }
    }
  }
  &#final {
    background-color: #fff;
    .inner-content {
      height: 100%;
    }
    .image {
      background-image: url("../assets/runner-fifth.jpg");
      max-width: 1311px;
      height: 100%;
      background-repeat: no-repeat;
      background-size: contain;
      display: flex;
      justify-content: flex-end;
      background-position: center;
      div {
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin: 30px;
        width: 45%;
        h2 {
          color: #fff;
          font-size: 45px;
          letter-spacing: 2px;
          font-weight: 700;
          font-family: $title-font;
          margin-bottom: 0px;
        }
        p {
          font-size: 20px;
          letter-spacing: 1px;
          color: #fff;
          line-height: 24px;
        }
      }
    }
  }
  img {
    object-fit: contain;
  }
  h2 {
    font-size: 50px;
    font-weight: 700;
    font-family: $title-font;
    margin-bottom: 0px;
  }
  h4 {
    text-transform: uppercase;
    color: $green;
  }
  .waitlist-button {
    width: 120px;
    padding: 10px;
    border: 1px solid $green;
    border-radius: 2px;
    background-color: $green;
    color: white;
  }
  .text-container {
    width: 30%;
    &.mobile {
      width: 90%;
    }
  }
}
</style>