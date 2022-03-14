<template>
  <div id="app">
    <Search />
    <My-component />
    <Counter />
    <UserCard />
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";
import Counter from "@/components/Counter.vue";
import UserCard from "@/components/UserCard.vue";
import Search from "@/components/Search.vue";

export default {
  name: "App",
  components: {
    MyComponent,
    Counter,
    UserCard,
    Search,
  },
};
</script>
