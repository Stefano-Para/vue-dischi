<template>

    <main>
        <div class="container_bg">

            <Albums
            v-if="!loading"
            
            :selectedGenre="currentGenre"
            @dataReady="setData"
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
    components: {
        Albums,
        Loader,
    },
    data () {
        return {
            loading: true,
            AllGenres: [],
            AllAuthors: [],
            currentGenre: ''
        }
    },
    setData: function(genresArray) {
        this.AllGenres = genresArray;
    },
    updateSelectedGenre: function() {
        this.currentGenre = newGenre;
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