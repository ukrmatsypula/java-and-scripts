<template>
  <div id="app">
    <My-component />
    <Counter />
    <UserCard />
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";
import Counter from '@/components/Counter.vue';
import UserCard from '@/components/UserCard.vue';

export default {
  name: "App",
  components: {
    MyComponent,
    Counter,
    UserCard,
  },
};
</script>
