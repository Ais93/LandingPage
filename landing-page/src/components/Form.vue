<template>
  <form class="form">
    <label for="fullName">Full Name</label>
    <input id="fullName" type="text" placeholder="Enter Full Name" />

    <label for="email">Email</label>
    <input id="email" type="email" placeholder="Enter Email" />

    <label for="phone">Phone</label>
    <input id="phone" type="number" placeholder="Enter Phone Number" />

    <label for="size">Size</label>
    <input id="size" type="number" placeholder="Enter Shoe Size" />
    <div class="buttons">
      <button class="close" @click="closeModal">Cancel</button>
      <button class="save" @click="saveForm">Join</button>
    </div>
  </form>
</template>

<script>
export default {
  methods: {
    closeModal() {
      this.$emit("close");
    },
    saveForm() {
      this.$emit("saved");
    },
  },
};
</script>

<style lang="scss" scoped>
$green: #a0c633;
.form {
  display: flex;
  flex-direction: column;
  input {
    margin: 10px 0px;
    height: 45px;
    margin-top: 0px;
    margin-bottom: 15px;
    border: none;
    background-color: #fafafa;
  }
  label {
    font-size: 12px;
    color: #999;
  }
  .buttons {
    display: flex;
    justify-content: space-between;
  }
  button {
    width: 120px;
    padding: 10px;
    border-radius: 2px;
    &.save {
      background-color: $green;
      color: white;
      border: 1px solid $green;
    }
    &.close {
      background-color: #fff;
      border: none;
      text-align: start;
    }
  }
}
</style>