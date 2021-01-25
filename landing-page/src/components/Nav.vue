<template>
  <div :class="{ change_color: scrollPosition > innerHeight }" class="parent">
    <mq-layout class="mq" mq="tablet+">
      <nav class="navigation">
        <img src="../assets/nike.png" />
        <button @click="openModal" class="waitlist-button">
          Join the waitlist
        </button>
      </nav>
    </mq-layout>
    <mq-layout mq="mobile">
      <nav class="navigation">
        <img src="../assets/nike.png" />
        <button @click="openModal" class="waitlist-button">
          Join the waitlist
        </button>
      </nav>
    </mq-layout>
  </div>
</template>

<script>
export default {
  props: {
    scrollPosition: Number,
    innerHeight: Number
  },
  methods: {
    openModal() {
      this.$emit("open");
    },
  },
};
</script>

<style lang="scss" scoped>
.change_color {
  background-color: black;
}
.parent {
  position: fixed;
  width: 100%;
  .mq {
    display: flex;
    justify-content: space-around;
  }
  .navigation {
    display: flex;
    justify-content: space-between;
    padding: 10px;
    max-width: 1440px;
    width: 100%;
    img {
      width: 70px;
      height: 25px;
      margin: 5px;
    }
  }
  .waitlist-button {
    width: 120px;
    padding: 10px;
    border: 1px solid #a0c633;
    border-radius: 2px;
    background-color: #a0c633;
    color: white;
  }
}
</style>