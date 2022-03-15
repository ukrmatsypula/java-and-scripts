<template>
  <div>
    <img :src="imgUrl" width="300" alt="" />
    <div>
      <h2>{{ title }}</h2>
      <p>{{ price }} грн</p>
      <p>Доступно для доставки {{ count }} штук</p>
      <button type="button" @click="addToCart">Добавить в корзину</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCart",
  props: {
    title: {
      type: String,
      default: "",
    },
    price: {
      type: Number,
      default: 0,
    },
    imgUrl: {
      type: String,
      default: "https://via.placeholder.com/300",
    },
    count: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    addToCart() {
      this.$emit("addToCart");
    },
  },
};
</script>

<style></style>
