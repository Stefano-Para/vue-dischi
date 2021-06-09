<template>
    <div id="loader_container">
        <h2>Albums are coming..</h2>
        <img src="https://img.pikbest.com/58pic/35/39/61/62K58PICb88i68HEwVnm5_PIC2018.gif!w340" alt="">
    </div>
  
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style lang="scss">
#loader_container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    background-color: #1E2D3B;
    img {
        width: 30%;
        height: 30%;
        margin: 0 auto;
    }
    h2 {
        color: white;
        text-align: center;
        text-transform: uppercase;
        margin-top: 50px;
    }
}
</style>