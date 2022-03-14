<template>
  <div id="app">
    <Search />
    <My-component />
    <Counter />
    <UserCard />
    <Cat />
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";
import Counter from "@/components/Counter.vue";
import UserCard from "@/components/UserCard.vue";
import Search from "@/components/Search.vue";
import Cat from '@/components/Cat.vue';

export default {
  name: "App",
  components: {
    MyComponent,
    Counter,
    UserCard,
    Search,
    Cat,
  },
};
</script>
