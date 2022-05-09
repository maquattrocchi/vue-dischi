<template>
    <header class="d-flex align-items-center">
        <img src="../assets/images/spotify-logo.png" alt="spotify-logo">
    </header>
</template>

<script>
export default {
    name: 'HeaderComponent',
}
</script>

<style scoped lang="scss">
@import '../style/vars';

    header{
        background: $card-color;
        height: 70px;
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        z-index: 2;
        
        img{
            margin-left: 1rem;
            width: 55px;
        }
    }
</style>
