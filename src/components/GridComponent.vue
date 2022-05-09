<template>
    <section class="container py-4">
        <search-component @search="setSearch($event)" :genres="genreFilter"/>

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
export default {
    name: 'GridComponent',
    components: { 
        SearchComponent, 
        CardComponent,
    },
    data(){
        return{
            discList:[],
            genreFilter: [],
            selectInput: '',
        }
    },
    computed: {
        filteredDisc(){
            if(this.selectInput === '') return this.discList
            return this.discList.filter((el)=> el.genre === this.selectInput)
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res)=>{
            this.discList = res.data.response
            this.discList.forEach((el)=>{
                if(!this.genreFilter.includes(el.genre)) this.genreFilter.push(el.genre)
            })
            console.log(this.genreFilter)
            console.log(res.data.response)
        }).catch((error)=>{
            console.log(error)
        })
    },
    
    methods: {
        setSearch(option){
            this.selectInput = option
        }
    }
}
</script>

<style lang="scss">
    .row{
        width: 80%;
    }
</style>