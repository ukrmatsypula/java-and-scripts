<template>
  <div id="app">
    <My-component />
    <Counter />
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";
import Counter from '@/components/Counter.vue';

export default {
  name: "App",
  components: {
    MyComponent,
    Counter,
  },
};
</script>
