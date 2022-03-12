<template>
  <div class="counter">
    <div class="minus" @click="minus">-</div>
    <input type="number" :value="counter" :min="minCount" :max="maxCount" />
    <div class="plus" @click="plus">+</div>
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
    minus() {
      if (this.counter <= this.minCount) {
        return;
      }
      this.counter--;
    },
    plus() {
      if (this.counter >= this.maxCount) {
        return;
      }
      this.counter++;
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
