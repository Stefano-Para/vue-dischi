<template>

    <main>
        <div class="container_bg">

            <Albums
            v-if="!loading"

            :selectedGenre="selectedGenre"
            @changedGenre="updateCurrentGenre"
            @genreReady="setData"
            />

            <Loader v-else />

        </div>
    </main>

</template>

<script>
import Albums from '../components/Albums.vue'
import Loader from './Loader.vue'

export default {
    name: 'Main',
    props: {
        selectedGenre: String
    },
    components: {
        Albums,
        Loader,
    },
    data () {
        return {
            loading: true,
            AllGenres: [],
            // AllAuthors: [],
            currentGenreDentroMain: '',
        }
    },
    methods: {
        setData: function(genresArray) {
            this.AllGenres = genresArray;
            // spostamento in app.vue
            this.$emit('genreReady', genresArray);
        },
        // questo è inutile perchè lo si fa solo in caso di emit
        updateCurrentGenre: function (newGenre) {
          this.currentGenre = newGenre;
          console.log(newGenre)
        }
    },
    created () {
        setTimeout( () => {
                    this.loading = false;
                }, 100)
    }
}
</script>


<style lang="scss">
    main {
        padding: 10px;
        background-color: #1E2D3B;
        height: 100%;
    }
    .container_bg {
        width: 60%;
        min-height: calc(100vh - 80px);
        margin: 0 auto;
    }
</style>