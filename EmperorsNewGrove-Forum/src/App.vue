<script>
export default {
  data: () => ({
    pokedex: [1, 2, 3],
  }),
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon/ditto').then(response => response.json())
    }
  }
}
</script>

<template>
  <h1>Practice Pulling from Back End</h1>
  <pre>{{ pokedex }}</pre>
  <button @click="fetchPokemon">Fetch Pokemon</button>
</template>

<style>

</style>