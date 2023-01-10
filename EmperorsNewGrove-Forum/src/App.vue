<script>
import ListCharacters from "./components/ListCharacters.vue"
import AddCharacter from "./components/AddCharacter.vue"
import Counter from "./components/Counter.vue"
import Statistics from "./components/CharacterStatistics.vue"

export default {
  data: () => ({
    favoritesList: [],
    listOfCharacters: [
      { name: 'Kuzco', species: ['Human', 'Llama'] },
      { name: 'Pacha', species: ['Human'] },
      { name: 'Ezma', species: ['Human', 'Cat'] },
      { name: 'Kronk', species: ['Human'] }
    ]
  }),
  components: {
    ListCharacters,
    Statistics,
    AddCharacter,
    Counter,
  }
}
</script>

<template>
  <ListCharacters :characters="listOfCharacters" />
  <hr>
  <Statistics :characters="listOfCharacters" />
  <hr>
  <AddCharacter :characters="listOfCharacters" />
  <hr>
  <Counter />
</template>
