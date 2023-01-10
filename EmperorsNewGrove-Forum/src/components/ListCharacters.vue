<script>
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
</template>