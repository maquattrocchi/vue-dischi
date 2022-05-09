<template>
    <div class="wrapper">
        <span class="loader"></span>
    </div>
</template>

<script>
export default {
    name: 'LoaderComponent'
}
</script>

<style lang="scss">
@import '../style/vars';
.wrapper{
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;

    .loader {
        width: 200px;
        height: 200px;
        display: inline-block;
        position: relative;
        transform: rotate(45deg);

        &::before{
            content: '';  
            box-sizing: border-box;
            width: 100px;
            height: 100px;
            position: absolute;
            left: 0;
            top: -100px;
            animation: animloader 4s ease infinite;
        }
        &::after{
            content: '';  
            box-sizing: border-box;
            position: absolute;
            left: 0;
            top: 0;
            width: 100px;
            height: 100px;
            background: rgba($title-color, 0.85);
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.15);
            animation: animloader2 2s ease infinite;
        }
}

}
@keyframes animloader {
    0% {
        box-shadow: 0 100px rgba($title-color, 0), 100px 100px rgba($title-color, 0), 100px 200px rgba($title-color, 0), 0px 200px rgba($title-color, 0);
    }
    12% {
        box-shadow: 0 100px $title-color, 100px 100px rgba($title-color, 0), 100px 200px rgba($title-color, 0), 0px 200px rgba($title-color, 0);
    }
    25% {
        box-shadow: 0 100px $title-color, 100px 100px $title-color, 100px 200px rgba($title-color, 0.103), 0px 200px rgba($title-color, 0);
    }
    37% {
        box-shadow: 0 100px $title-color, 100px 100px $title-color, 100px 200px $title-color, 0px 200px rgba($title-color, 0);
    }
    50% {
        box-shadow: 0 100px $title-color, 100px 100px $title-color, 100px 200px $title-color, 0px 200px $title-color;
    }
    62% {
        box-shadow: 0 100px rgba($title-color, 0), 100px 100px $title-color, 100px 200px $title-color, 0px 200px $title-color;
    }
    75% {
        box-shadow: 0 100px rgba($title-color, 0), 100px 100px rgba($title-color, 0), 100px 200px $title-color, 0px 200px $title-color;
    }
    87% {
        box-shadow: 0 100px rgba($title-color, 0), 100px 100px rgba($title-color, 0), 100px 200px rgba($title-color, 0), 0px 200px $title-color;
    }
    100% {
        box-shadow: 0 100px rgba($title-color, 0), 100px 100px rgba($title-color, 0), 100px 200px rgba($title-color, 0), 0px 200px rgba($title-color, 0);
    }
}

@keyframes animloader2 {
    0% {
        transform: translate(0, 0) rotateX(0) rotateY(0);
    }
    25% {
        transform: translate(100%, 0) rotateX(0) rotateY(180deg);
    }
    50% {
        transform: translate(100%, 100%) rotateX(-180deg) rotateY(180deg);
    }
    75% {
        transform: translate(0, 100%) rotateX(-180deg) rotateY(360deg);
    }
    100% {
        transform: translate(0, 0) rotateX(0) rotateY(360deg);
    }
}
</style>