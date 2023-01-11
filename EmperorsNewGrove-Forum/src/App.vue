<script>
import HomePage from "./components/HomePage.vue"
import LoginPage from "./components/LoginPage.vue"
import UserPage from "./components/UserPage.vue"
import BaseLayout from "./components/BaseLayout.vue"
import ListCharacters from "./components/ListCharacters.vue"
import AddCharacter from "./components/AddCharacter.vue"
import Counter from "./components/Counter.vue"
import Statistics from "./components/CharacterStatistics.vue"

export default {
  data: () => ({
    currentPage: "Home",
    listOfCharacters: [
      { name: 'Kuzco', species: ['Human', 'Llama'] },
      { name: 'Pacha', species: ['Human'] },
      { name: 'Ezma', species: ['Human', 'Cat'] },
      { name: 'Kronk', species: ['Human'] }
    ]
  }),
  components: {
    HomePage,
    LoginPage,
    UserPage,
    ListCharacters,
    Statistics,
    AddCharacter,
    Counter,
    BaseLayout,
  },
  methods: {
    showHomePage() {
      this.currentPage = "Home"
    },
    showLoginPage() {
      this.currentPage = "Login"
    },
    showUserPage() {
      this.currentPage = "User"
    },
    showListCharactersPage() {
      this.currentPage = "Characters"
    },
    showCounterPage() {
      this.currentPage = "Counter"
    }
  },
}
</script>

<template>
  <header class="header">
    <span class="logo">
      <img src="@/assets/vue-heart.png" width="30" />C'est La Vue
    </span>
    <nav class="nav">
      <a href="#" @click.prevent="showHomePage">Home</a>
      <a href="#" @click.prevent="showLoginPage">Login</a>
      <a href="#" @click.prevent="showUserPage">User</a>
      <a href="#" @click.prevent="showListCharactersPage">Characters</a>
      <a href="#" @click.prevent="showCounterPage">Counter</a>
    </nav>
  </header>
  <HomePage v-if="currentPage === 'Home'" />
  <LoginPage v-else-if="currentPage === 'Login'" />
  <UserPage v-else-if="currentPage === 'User'" />
  <ListCharacters v-else-if="currentPage === 'Characters'" :characters="listOfCharacters" />
  <Counter v-else-if="currentPage === 'Counter'" />
</template>

<style>
* {
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
  margin: 0;
  padding: 0;
}

.header {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 1rem;
  border-bottom: 1px solid #ccc;
}

span.logo {
  display: flex;
  align-items: center;
  font-weight: bold;
  font-size: 1.2rem;
}

span.logo img {
  margin-right: 8px;
}

.nav {
  display: flex;
  align-items: center;
}

.nav a {
  padding: 0.5rem;
  font-size: 0.9rem;
}

.nav a:last-child {
  padding-right: 0;
}
</style>