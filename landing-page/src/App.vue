<template>
  <div id="app">
    <Nav @open="openModal" />
    <LandingPage @open="openModal" />
    <modal :show="show" @close="closeModal" />
  </div>
</template>

<script>
import LandingPage from "./pages/LandingPage";
import Nav from "./components/Nav";
// import Footer from "./components/Footer";
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    LandingPage,
    Nav,
    // Footer,
    Modal,
  },
  data() {
    return {
      show: false,
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
