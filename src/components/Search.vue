<template>
  <div>
    <input type="text" @input="search($event.target.value)" />
    <p>Всего имен: {{ names.length }}, совпадений: {{ getFilteredName.length }}</p>
  </div>
</template>

<script>
export default {
  data: () => ({
    searchText: "",
    names: ["Данил", "Василий", "Дмитрий", "Григорий", "Максим"],
  }),
  computed: {
    getFilteredName() {
      return this.names.filter((name) =>
        name.toLowerCase().includes(this.searchText.toLowerCase())
      );
    },
  },
  methods: {
    search(searchQuery) {
      return (this.searchText = searchQuery);
    },
  },
};
</script>
