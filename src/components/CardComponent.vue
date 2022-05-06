<template>
    <div class="card h-100">
        <img :src="item.poster" class="card-img-top" alt="...">
        <div class="card-body px-0">
            <h5 class="cs_title">{{item.title}}</h5>
            <div class="mb-2 cs_text">{{item.author}}</div>
            <div class="cs_text">{{item.year}}</div>
        </div>
    </div>
        <!-- poster: 'https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg', title: 'New Jersey', author: 'Bon Jovi', genre: 'Rock', year: '1988' -->
        <!-- <img :src="item.poster" :alt="item.title" class="img-fluid">
        <h1>{{item.title}}</h1>
        <div>{{item.author}}</div>
        <div>{{item.year}}</div>
        </div> -->
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