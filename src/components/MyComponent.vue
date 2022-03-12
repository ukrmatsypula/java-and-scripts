<template>
  <div class="root">
    <input
      type="email"
      :value="email"
      @input="emailInput($event.target.value)"
    />
    <input
      type="text"
      :value="password"
      @input="passwordValue($event.target.value)"
    />

    email: {{ email }} password: {{ password }}
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data: () => ({
    email: "HelloWorld@gmail.com",
    password: "pass",
  }),
  methods: {
    emailInput(value) {
      this.email = value;
    },
    passwordValue(passwordValue) {
      this.password = passwordValue;
    },
  },
};
</script>
