<template>
  <div id="dashboard">
    <h1>That's the dashboard!</h1>
    <p>You should only get here if you're authenticated!</p>
    <p>Your email address: {{ displayEmail }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  created() {
    this.$store.dispatch('fetchUser')
  },
  computed: {
    displayEmail() {
      return !this.$store.getters.user ? false : this.$store.getters.user.email
    }
  }
}
</script>

<style scoped>
h1,
p {
  text-align: center;
}

p {
  color: red;
}
</style>
