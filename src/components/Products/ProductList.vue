<template>
  <div>
    <h1>Писменные столы</h1>
    <MyInput v-model="searchText" />
    <button type="button">Найти</button>
    {{ searchText }}
    <ul>
      <li v-for="(product, index) in products" :key="index">
        <ProductCart
          :title="product.title"
          :price="product.price"
          :img-url="product.imgUrl"
          :count="product.count"
          @addToCart="addToCart(product)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import ProductCart from "@/components/Products/ProductCart.vue";
import MyInput from "@/components/MyInput.vue";

export default {
  name: "ProductList",
  components: {
    ProductCart,
    MyInput,
  },
  data: () => ({
    searchText: "",
    products: [
      {
        title: "Стол Jim",
        price: 19999,
        imgUrl:
          "https://hoff.ru/upload/iblock/8c9/8c989500ee8639b9e3aa267b1888b4af.jpg",
        count: 30,
      },
      {
        title: "Стол Monako",
        price: 17199,
        imgUrl:
          "https://hoff.ru/upload/iblock/af2/af2d37161f217d4f489373be7da4a7a0.jpg",
        count: 20,
      },
      {
        title: "Стол с двумя ящиками Кварт MD 768",
        price: 10999,
        imgUrl:
          "https://hoff.ru/upload/iblock/1cc/1ccb33b50e3e9cfa08629bf455e41855.jpg",
        count: 23,
      },
    ],
  }),
  methods: {
    addToCart(product) {
      console.log("Товар успешно добавлен в корзину ", { ...product });
    },
  },
};
</script>

<style></style>
