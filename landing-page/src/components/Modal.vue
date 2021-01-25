<template>
  <transition name="fade">
    <div class="modal" v-if="show">
      <div class="modal__backdrop" @click="closeModal" />

      <div class="modal__dialog">
        <div v-if="!saved" class="modal__header">
          <h2> Signup to our waitlist</h2>
          <span>Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.</span>
          <button type="button" class="modal__close" @click="closeModal">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 352 512">
              <path
                fill="currentColor"
                d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
              ></path>
            </svg>
          </button>
        </div>

        <div v-if="!saved"  class="modal__body">
          <Form @saved="savedForm" />
        </div>
        <div v-if="saved" class="modal__header">
          <h2> You're all signed up to our waitlist!</h2>
          <button type="button" class="modal__close" @click="closeModal">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 352 512">
              <path
                fill="currentColor"
                d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
              ></path>
            </svg>
          </button>
        </div>
        <div v-if="saved"  class="modal__body">
          <p>Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.
            Ipsum laborum incididunt sunt nulla sint. Magna fugiat enim pariatur irure.
          </p>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import Form from "../components/Form";
export default {
  components: {
    Form,
  },
  props: {
    show: Boolean,
  },
  data() {
    return {
      saved: false,
    };
  },
  methods: {
    closeModal() {
      this.$emit('close');
    },
    savedForm() {
      this.saved = true;
    },
  }
};
</script>


<style lang="scss" scoped>
.modal {
  overflow-x: hidden;
  overflow-y: auto;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 9;
  &__backdrop {
    background-color: rgba(0, 0, 0, 0.3);
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 1;
  }
  &__dialog {
    background-color: #ffffff;
    position: relative;
    width: 640px;
    margin: 50px auto;
    display: flex;
    flex-direction: column;
    border-radius: 5px;
    z-index: 2;
    padding: 30px;
    @media screen and (max-width: 992px) {
      width: 90%;
    }
  }
  &__close {
    width: 25px;
    height: 25px;
    border: none;
    background-color: inherit;
    position: absolute;
    top: 10px;
    right: 10px;
  }
  &__header {
    padding-bottom: 40px;
    display: flex;
    flex-direction: column;
    position: relative;
    h2 {
      font-family: 'Montserrat', sans-serif;
      font-size: 40px;
      margin-bottom: 10px;
    }
  }
  &__body {
    overflow: auto;
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
  &__footer {
    padding: 10px 20px 20px;
  }
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>