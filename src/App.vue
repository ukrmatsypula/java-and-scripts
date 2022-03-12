<template>
  <div id="app">
    <My-component />
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";

export default {
  name: "App",
  components: {
    MyComponent,
  },
};
</script>
