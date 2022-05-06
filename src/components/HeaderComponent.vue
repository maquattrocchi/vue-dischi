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
@import '../style/general';
    header{
        background: $card-color;
        height: 70px;
        
        img{
            margin-left: 1rem;
            width: 55px;
        }
    }
</style>
