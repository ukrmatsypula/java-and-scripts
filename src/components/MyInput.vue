<template>
  <div>
    <input type="text" @input="$emit('input', $event.target.value)" />
  </div>
</template>

<script>
export default {
  name: "MyInput",
  model: {
    prop: "value",
    event: "input",
  },
};
</script>

<style></style>
