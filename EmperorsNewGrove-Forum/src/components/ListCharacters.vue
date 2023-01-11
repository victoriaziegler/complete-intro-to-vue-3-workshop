<script>
import BaseLayout from "./BaseLayout.vue"
import AddCharacter from "./AddCharacter.vue"
import Statistics from "./CharacterStatistics.vue"

export default {
    props: ["characters"],
    data: () => ({
        favoritesList: [],
    }),
    methods: {
        createFavoritesList(character) {
            this.favoritesList.push(character)
        }
    },
    components: {
        Statistics,
        AddCharacter,
        BaseLayout,
    },
}
</script>

<template>
    <h1>Emperor's New Groove</h1>
    <h2>List of Characters</h2>
    <p v-if="characters.length == 0">There are no characters</p>
    <ul>
        <li v-for="character in characters">
            <p>{{ character.name }}</p>
            <button v-on:click="createFavoritesList(character)">Favorite</button>
        </li>
    </ul>
    <p>
        <span v-for="(character, index) in characters">
            {{ character.name }}{{ index === characters.length - 1 ? '' : ', '}}
        </span>
    </p>
    <hr>
    <h2>List Favorite Characters</h2>
    <p v-if="favoritesList.length == 0">Favorites List is Empty</p>
    <ul>
        <li v-for="favorite in favoritesList">{{ favorite.name }}</li>
    </ul>
    <BaseLayout>
        <template v-slot:one>
            <AddCharacter :characters="characters" />
        </template>
        <template v-slot:two>
            <Statistics :characters="characters" />
        </template>
    </BaseLayout>
</template>