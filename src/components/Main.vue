<template>

    <main>
        <div class="container_bg">
            <Albums />
        </div>
    </main>

</template>

<script>
import Albums from '../components/Albums.vue'
    export default {
        name: 'Main',
        components: {
            Albums
        }
    }
</script>


<style lang="scss">
    main {
        padding: 10px;
        background-color: #1E2D3B;
    }
    .container_bg {
        width: 60%;
        height: 100%;
        margin: 0 auto;
        background-color: orange;
    }
</style>