<template>
  <div id="app">
    <Nav :scroll-position="scrollPosition" :inner-height="innerHeight" @open="openModal" />
    <LandingPage @open="openModal" />
    <modal :show="show" @close="closeModal" />
  </div>
</template>

<script>
import LandingPage from "./pages/LandingPage";
import Nav from "./components/Nav";
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    LandingPage,
    Nav,
    Modal,
  },
  data() {
    return {
      show: false,
      scrollPosition: null,
      innerHeight: null,
    };
  },
  methods: {
    closeModal() {
      this.show = false;
      document.querySelector("body").classList.remove("overflow-hidden");
    },
    openModal() {
      this.show = true;
      document.querySelector("body").classList.add("overflow-hidden");
    },
    updateScroll() {
      this.scrollPosition = window.scrollY;
      this.innerHeight = window.innerHeight;
      console.info(this)
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
  font-family: "Inter", sans-serif;
}
</style>
