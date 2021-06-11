<template>

    <header>
            <img src="../assets/spotify.png" alt="">

            <!-- perchè selected genre prende direttamente il genere selezionato? è perchè sotto seleziona da { genre }? -->
            <select
            v-model="selectedGenre"
            @change="$emit('changedGenre', selectedGenre)"
            >
                <option value="">Seleziona un Genere</option>
                <option
                v-for="(genre, index) in genres"
                :key="index"
                :value="genre">{{ genre }}</option>
            </select>
    </header>
</template>

<script>

    export default {
        name: 'Header',
        data: function() {
            return {
            selectedGenre: ''
            }
        },
        props: {
            "genres": Array
        }
    }
</script>


<style lang="scss" scoped>

    header {
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: #2E3A46;
        height: 60px;
        width: 100%;
    }
    img {
        width: 40px;
        height: 40px;
    }
    
</style>