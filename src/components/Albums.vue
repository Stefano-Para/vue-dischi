<template>
    <div class="container_albums">
            <ul>
                <li>
                    <a href="">
                        <img src="https://files.slack.com/files-tmb/T91QPE3BP-F02420JKYMV-6589a5cbdf/spotify_720.png" alt="">
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
    export default {
        name: 'Albums'
    }
</script>

<style lang="scss" scoped>
    ul {
        display: flex;
        padding: 0;
        li {
            list-style: none;
            background-color: blue;
            width: 22%;
            padding: 15px;
            h2  {
                color: white;
            }
            h4 {
                color: lightgrey;
            }
            h5 {
                color: tgrey;
            }
        }
    }
    
    
</style>