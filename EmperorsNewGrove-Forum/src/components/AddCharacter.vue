<script>
export default {
    props: ["characters"],
    data: () => ({
        newCharacter: { name: '', species: [] },
    }),
    methods: {
        addCharacter() {
            this.characters.push(this.newCharacter)
            this.newCharacter = { name: '' }
        },
    }
}
</script>

<template>
    <h2>Add a Character</h2>
    <div>
        <pre>{{ newCharacter }}</pre>
        <label for="addCharacter">Add Character Name: </label>
        <input type="text" v-model="newCharacter.name" @keyup.enter="addCharacter(newCharacter)" />
        <label for="addCharacter">Add Character Species: </label>
        <input type="text" v-model="newCharacter.species" @keyup.enter="addCharacter(newCharacter)" />
        <button v-on:click="addCharacter">Add</button>
    </div>
</template>