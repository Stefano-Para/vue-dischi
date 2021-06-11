<template>
  <div id="app">
    <!-- header  -->
    <Header
      :genres="AllGenresApp"
      @changedGenre="updateCurrentGenre"
    />
    <!-- main  -->
    <Main
      :selectedGenre="currentGenre"
      
      @genreReady="setData"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Main,
    Header
  },
  data () {
    return {
      // array dei generi DENTRO AD APP 
      AllGenresApp: [],
      currentGenre: ''
    }
  },
  methods: {
        setData: function(genresArray) {
            this.AllGenresApp = genresArray;
            // spostamento in app.vue
            this.$emit('genreReady', genresArray);
            // console.log(genresArray)
        },
        updateCurrentGenre: function (newGenre) {
          this.currentGenre = newGenre;
          console.log(newGenre)
        }
    },
}
</script>

<style lang="scss"> 
// general rules
@import '~bootstrap/scss/bootstrap.scss';
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
// main {
//   font-family: 'roboto', sans-serif;
// }
</style>
