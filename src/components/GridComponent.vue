<template>
    <section class="container">
        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5 gy-3 w-75 m-auto">
            <div v-for="(disc, index) in discList" :key="index" class="col">
                <card-component :item="disc"/>
            </div>
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import CardComponent from './CardComponent.vue';
export default {
    name: 'GridComponent',
    components: { 
      CardComponent 
    },
    data(){
        return{
            discList:[],
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res)=>{
            this.discList = res.data.response
        }).catch((error)=>{
            console.log(error)
        })
    }
}
</script>

<style lang="scss">


</style>