<template>
        <div v-if="!loading" class="container_albums">
                <ul>
                    <li v-for="(album, index) in albums"
                    :key="index">
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
        <Loader v-else />
</template>

<script>
// senza tilde perchè mi porta automaticamente in node_modus 
import axios from 'axios'
import Loader from './Loader.vue'


export default {
    name: 'Albums',
    components: {
    Loader
    },
    data () {
        return {
            albums: [],
            loading: true
        }
    },
    created () {
        axios
            .get ('https://flynn.boolean.careers/exercises/api/array/music')
            .then ( (exportAxios) => {
                this.albums = exportAxios.data.response;
                setTimeout( () => {
                    this.loading = false;
                }, 2800)
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
    justify-content: space-between;
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
                width: 95%;
                height: 120px;
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