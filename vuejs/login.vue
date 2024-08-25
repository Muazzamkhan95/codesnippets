<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name:</label>
      <input type="text" v-model="name" />
      <span v-if="nameError" class="error">{{ nameError }}</span>
    </div>
    <div>
      <label for="email">Email:</label>
      <input type="email" v-model="email" />
      <span v-if="emailError" class="error">{{ emailError }}</span>
    </div>
    <button type="submit" :disabled="!isFormValid">Submit</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: ''
    };
  },
  computed: {
    nameError() {
      if (!this.name) return 'Name is required';
      return null;
    },
    emailError() {
      const validEmail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!this.email) return 'Email is required';
      if (!validEmail.test(this.email)) return 'Enter a valid email';
      return null;
    },
    isFormValid() {
      return !this.nameError && !this.emailError;
    }
  },
  methods: {
    submitForm() {
      if (this.isFormValid) {
        alert('Form submitted successfully!');
      }
    }
  }
};
</script>

<style>
.error {
  color: red;
  font-size: 0.875rem;
}
</style>
