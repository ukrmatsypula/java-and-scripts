<template>
  <div class="flex-cat">
    <div>
      <img
        v-if="isCatVisible"
        src="https://media.istockphoto.com/photos/cat-with-a-hot-dog-and-juice-picture-id946181408?s=612x612"
        :style="dinamicRotate"
        :class="{
          isShadow: filter.shadow,
          isSepia: filter.sepia,
          isBorder: filter.isBorder,
        }"
        alt="cat"
      />
      <p v-else>Кот скоро вернется...</p>
    </div>
    <button @click="isCatVisible = !isCatVisible">{{ showHideText }}</button>
    <button @click="filter.shadow = !filter.shadow">add shadow</button>
    <button @click="filter.sepia = !filter.sepia">sepia</button>
    <button @click="filter.isBorder = !filter.isBorder">add border</button>

    <input
      type="range"
      :value="filter.rotate.currentValue"
      :min="filter.rotate.minValue"
      :max="filter.rotate.maxValue"
      @input="filter.rotate.currentValue = $event.target.value"
    />
    {{ dinamicRotate }}
  </div>
</template>

<script>
export default {
  name: "cat",
  data: () => ({
    isCatVisible: true,
    filter: {
      rotate: {
        minValue: 0,
        maxValue: 360,
        currentValue: 0,
      },
      shadow: false,
      sepia: false,
      isBorder: false,
    },
  }),
  computed: {
    dinamicRotate() {
      return `transform: rotate(${this.filter.rotate.currentValue}deg)`;
    },
    showHideText() {
      return this.isCatVisible ? "Спрятать" : "Показать";
    },
  },
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

    & > img.isShadow {
      box-shadow: 0 10px 25px #000;
    }

    & > img.isSepia {
      filter: sepia(1);
    }

    & > img.isBorder {
      border: 10px dotted brown;
    }
  }
}
</style>
