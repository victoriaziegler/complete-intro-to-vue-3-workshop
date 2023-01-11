<script>
import BaseLayout from "./components/BaseLayout.vue"
import ListCharacters from "./components/ListCharacters.vue"
import AddCharacter from "./components/AddCharacter.vue"
import Counter from "./components/Counter.vue"
import Statistics from "./components/CharacterStatistics.vue"

export default {
  data: () => ({
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
    BaseLayout,
  }
}
</script>

<template>
  <BaseLayout>
    <template v-slot:one>
      <AddCharacter :characters="listOfCharacters" />
    </template>
    <template v-slot:two>
      <Statistics :characters="listOfCharacters" />
    </template>
  </BaseLayout>
  <hr>
  <ListCharacters :characters="listOfCharacters" />
  <hr>
  <Counter />
</template>
