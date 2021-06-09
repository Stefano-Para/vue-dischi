<template>
    <div class="container_albums">
            <ul>
                <li>
                    <a href="">
                        <img src="../assets/spotify.png" alt="">
                        <h2>
                            Album
                        </h2>
                        <h4>
                            Artista
                        </h4>
                        <h5>
                            Data
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
        data () {
            return {
              array: []  
            }
        },
        created () {
            axios
                .get ('https://flynn.boolean.careers/exercises/api/array/music')
                .then ( (exportAxios) => {
                    exportAxios.data.response
                    console.log(exportAxios)
                    }
                )
        }
    }
    
</script>

<style lang="scss" scoped>
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
            background-color: blue;
            width: 20%;
            padding: 15px;
            margin: 15px;
            text-align: center;
            a {
                text-decoration: none;
                cursor: pointer;
                img {
                    width: 80px;
                }
                h2  {
                    color: white;
                }
                h4 {
                    color: lightgrey;
                }
                h5 {
                    color: grey;
                }
            }
        }
    }
    
    
</style>