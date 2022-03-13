<template>
  <div class="counter">
    <button type="button" @click="decreaseCount">+</button>

    <input type="number" :value="counter" :min="minCount" :max="maxCount" />

    <button type="button" @click="increaseCount">-</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data: () => ({
    counter: 1,
    minCount: 1,
    maxCount: 10,
  }),
  methods: {
    decreaseCount() {
      if (this.counter < this.maxCount) {
        this.counter++;
      }
    },
    increaseCount() {
      if (this.counter > this.minCount) {
        this.counter--;
      }
    },
  },
};
</script>

<style scoped>
.minus,
.plus {
  display: inline-block;
  width: 20px;
  height: 20px;
  border: 1px solid #ccc;
  text-align: center;
  cursor: pointer;
  user-select: none;
}
</style>
