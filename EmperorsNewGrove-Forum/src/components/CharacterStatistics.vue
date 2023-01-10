<script>
export default {
    props: ["characters"],
    computed: {
        speciesStatistics() {
            const species = ['Human', 'Cat', 'Llama', 'Squirrel']
            const statistics = {
                Human: 0,
                Cat: 0,
                Llama: 0,
                Squirrel: 0
            }

            this.characters.forEach(character => {
                species.forEach(species => {
                    if (character.species.indexOf(species) > -1) {
                        statistics[species] += 1
                    }
                })
            })
            return statistics
        }
    },
}
</script>

<template>
    <div>
        <h2>Statistics</h2>
        <ul>
            <li v-for="(stat, type) in speciesStatistics">{{ type }}: {{ stat }}</li>
        </ul>
    </div>
</template>