<template>
        <div class="container_albums">
            <ul>
                <li v-for="(album, index) in filteredAlbums"
                :key="index">
                    {{ selectedGenre }}
                    <a href="">
                        <img :src="album.poster" alt="">
                        <h2>
                            {{ album.title }}
                        </h2>
                        <h4>
                            {{ album.author }}
                        </h4>
                        <h5>
                            {{ album.year }}
                        </h5>
                    </a>
                </li>
            </ul>
        </div>

</template>

<script>
// senza tilde perchè mi porta automaticamente in node_modus 
import axios from 'axios'



export default {
    name: 'Albums',
    props: {
        selectedGenre: String
    },
    computed: {
        filteredAlbums: function () {
            if (this.selectedGenre == "") {
                return this.albums;
            }
            
            return this.albums.filter(
                element => element.genre == this.selectedGenre
            );
        }
    },
    data () {
        return {
            albums: [],
            genres: [],
        }
    },
    created () {
        axios
            .get ('https://flynn.boolean.careers/exercises/api/array/music')
            .then ( (exportAxios) => {
                this.albums = exportAxios.data.response;
                // ciclo tutti i dischi 
                this.albums.forEach(
                    (element) => {
                        if (!this.genres.includes(element.genre)) {
                            this.genres.push(element.genre);
                        }
                    }
                );
                this.$emit('genreReady', this.genres);
                }
            )
    }
}
    
</script>

<style lang="scss" scoped>
.loader {
    color: white;
}
ul {
    display: flex;
    flex-wrap: wrap;
    padding: 0;
    li {
        display: flex;
        flex-direction: column;
        align-items: center;
        list-style: none;
        background-color: #2E3A46;
        width: 16%;
        height: 270px;
        padding: 15px;
        margin: 15px;
        text-align: center;
        a {
            text-decoration: none;
            cursor: pointer;
            img {
                max-width: 105px;
                max-height: 120px;
            }
            h2  {
                color: white;
                margin: 10px 0 0 0;
                text-transform: uppercase;
                font-size: 16px;
            }
            h4 {
                margin: 20px 0 0 0;
                font-size: 12px;
                color: lightgrey;
            }
            h5 {
                margin: 0;
                font-size: 12px;
                color: grey;
            }
        }
    }
}
    
    
</style>