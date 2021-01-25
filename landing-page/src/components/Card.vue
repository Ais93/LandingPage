<template>
  <div class="card">
    <img :src="require(`../assets/${card.icon}`)">
    <h5>{{ card.title }}</h5>
    <p> {{ card.text }} </p>
  </div>
</template>

<script>
export default {
  props: {
    card: Object,
  }
}
</script>

<style lang="scss" scoped>
.card {
  width: 350px;
  height: 350px;
  background-color: #FAFAFA;
  border: 1px solid #FAFAFA;
  border-radius: 5px;
  padding: 40px;
  margin: 25px;
  h5 {
    font-weight: 700;
    font-size: 30px;
    font-family: 'Montserrat', sans-serif;
    margin-bottom: 0px;
  }
  p {
    font-size: 15px;
  }
}
</style>