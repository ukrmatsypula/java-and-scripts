<template>
  <div class="conatiner">
    <div class="user-card">
      <h1>Научу зарабатывать от 50 000р. в час</h1>
      <div class="main-information flex">
        <img
          src="https://gitlab.com/DanilChushko/vue-lessons/-/raw/lesson-1-hw/src/assets/images/%D0%BA%D0%BE%D1%83%D1%87.jpg"
          width="500px"
        />
        <div class="info">
          <h2>{{ "text" }}</h2>
          <strong>Бизнес-коуч</strong>
          <ul class="list">
            <li>
              Учу делать РЕАЛЬНЫЕ бабки, на себя просто не хватило времени
            </li>
            <li>
              НЕ знаю, что такое "Успешный Успех", но знаю, что нужно ТЕБЕ!
            </li>
            <li>Пообещал, что побреюсь, когда кого-нибудь ОБМАНУ.</li>
          </ul>
        </div>
      </div>
      <p>Участников: {{ users.length }}</p>
      <ul class="list">
        <li v-for="(user, index) in users" :key="index">
          {{ user.firstName }} {{ user.secondName }} {{ user.lastName }}
        </li>
      </ul>

      <button @click="currentPage--">Назад</button>
      <button v-for="page in pages" :key="page" @click="currentPage = page">
        {{ page }}
      </button>
      <button @click="currentPage++">Вперед</button>

      <p>Страница: {{ currentPage }} из {{ pages }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserCard",
  data() {
    return {
      firstName: "Игнатий",
      secondName: "Иларионович",
      lastName: "Богатов",
      users: [
        {
          firstName: "Игнатий",
          secondName: "Иларионович",
          lastName: "Богатов",
        },
        {
          firstName: "Игнатий",
          secondName: "Иларионович",
          lastName: "Богатов",
        },
        {
          firstName: "Игнатий",
          secondName: "Иларионович",
          lastName: "Богатов",
        },
      ],
      pages: 3,
      currentPage: 1,
    };
  },

  methods: {
    loadUsers(page) {
      console.log(`Загрузка пользователей: Страница ${page}`);
    },
  },

  watch: {
    currentPage(newValue) {
      this.loadUsers(newValue);
    },
  },
};
</script>

<style lang="scss" scoped>
.user-card {
  margin-top: 40px;
}
.info {
  margin-left: 50px;
}
h2 {
  margin-bottom: 14px;
}
</style>
