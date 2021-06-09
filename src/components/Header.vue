<template>

    <header>
            <img src="../assets/spotify.png" alt="">
    </header>
</template>

<script>

    export default {
        name: 'Header'
    }
</script>


<style lang="scss" scoped>

    header {
        padding: 10px;
        display: flex;
        align-items: center;
        background-color: #2E3A46;
        height: 60px;
        width: 100%;
    }
    img {
        width: 40px;
        height: 40px;
    }
    
</style>