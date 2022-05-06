<template>
    <div class="card h-100">
        <img :src="item.poster" class="card-img-top" alt="...">
        <div class="pt-3">
            <h5 class="cs_title">{{item.title}}</h5>
            <div class="cs_text">{{item.author}}</div>
            <div class="cs_text">{{item.year}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'GridComponent',
    props: {
        item: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/vars';
    .card{
        padding: 1rem;
        background-color: $card-color;
        border: none;
        text-align: center;

        .cs_title{
            text-transform: uppercase;
            color: $title-color;
            font-weight: bold;
        }
        .cs_text{
            color: $text-color;
            font-size: 1.3rem;
        }

    }
</style>