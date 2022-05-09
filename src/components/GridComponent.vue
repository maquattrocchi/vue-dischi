<template>
    <section class="container py-4">

        <search-component @search="setSearchGenre($event)" :list="genreFilter" info="genre"/>
        <search-component @search="setSearchArtist($event)" :list="artistFilter" info="artist"/>

        <loader-component v-if="loading"/>

        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 gy-3 m-auto">
            <div v-for="(disc, index) in filteredDisc" :key="index" class="col">
                <card-component :item="disc"/>
            </div>
        </div>

    </section>
</template>

<script>
import axios from 'axios';
import SearchComponent from './SearchComponent.vue';
import CardComponent from './CardComponent.vue';
import LoaderComponent from './LoaderComponent.vue';

export default {
    name: 'GridComponent',
    components: { 
        SearchComponent, 
        CardComponent,
        LoaderComponent,
    },
    data(){
        return{
            discList:[],
            genreFilter: [],
            artistFilter: [],
            genreInput: '',
            artistInput: '',
            loading: false,
        }
    },
    computed: {
        filteredDisc(){
            if(this.genreInput === '' && this.artistInput === ''){
                return this.discList;
            }else if (this.artistInput === ''){
                return this.discList.filter((el)=>el.genre === this.genreInput);
            } else if (this.genreInput === ''){
                return this.discList.filter((el)=>el.author === this.artistInput);
            }else{
                return this.discList.filter((el)=> el.genre === this.genreInput).filter((el)=>el.author === this.artistInput);
            }
        },
    },
    mounted(){
        this.loading = true;
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res)=>{
            this.discList = res.data.response;
            this.discList.forEach((el)=>{
                if(!this.genreFilter.includes(el.genre)) this.genreFilter.push(el.genre);
                if(!this.artistFilter.includes(el.author)) this.artistFilter.push(el.author);
            })
            this.loading = false;
        }).catch((error)=>{
            console.log(error);
            this.loading = false;
        })
    },
    methods: {
        setSearchGenre(txt){
            this.genreInput = txt;
        },
        setSearchArtist(txt){
            this.artistInput = txt;
        }
    },
}
</script>

<style lang="scss">
.row{
    width: 80%;
}
</style>