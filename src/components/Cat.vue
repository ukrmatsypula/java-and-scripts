<template>
  <div class="flex-cat">
    <div>
      <img
        v-if="isCatVisible"
        src="https://media.istockphoto.com/photos/cat-with-a-hot-dog-and-juice-picture-id946181408?s=612x612"
        alt="cat"
      />
      <p v-else>Кот скоро вернется...</p>
    </div>
    <button @click="isCatVisible = !isCatVisible">Спрятать / Показать</button>
  </div>
</template>

<script>
export default {
  name: "cat",
  data: () => ({
    isCatVisible: true,
  }),
};
</script>

<style lang="scss">
.flex-cat {
  display: flex;
  align-items: center;

  div {
    width: 630px;
    height: 630px;
    background-color: #ccc;
  }
}
</style>
