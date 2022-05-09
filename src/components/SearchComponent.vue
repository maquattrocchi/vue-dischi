<template>
    <div>
        <div class="input-group mb-3">
            <label class="input-group-text" for="genre">Search by genre</label>
            <select class="form-select" name="genre" id="genre" v-model="searchGenre" @change="searchDisc">
                <option value="">All</option>
                <option :value="genre" v-for="genre in genres" :key="genre">{{genre}}</option>
            </select>
        </div>
        <div class="input-group mb-3">
            <label class="input-group-text" for="artist">Search by artist</label>
            <select class="form-select" name="artist" id="artist" v-model="searchArtist" @change="searchDisc">
                <option value="">All</option>
                <option :value="artist" v-for="artist in artists" :key="artist">{{artist}}</option>
            </select>
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'SearchComponent',
    props: ['genres', 'artists'],
    data(){
        return {
            searchGenre: '',
            searchArtist: '',
        }
    },
    methods:{
        searchDisc(){
            this.$emit('search', [this.searchGenre, this.searchArtist])
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/vars';
    .input-group-text {
        font-size: 1.3rem;
        color: $title-color;
        background-color: $card-color;
        border-color: $bg-color;
        text-transform: uppercase;
    }
    .form-select{
        background-color: $card-color;
        color: $title-color;
        border-color: $bg-color;
        background-image: none;
        appearance: auto;
        -webkit-appearance: auto;

    }
</style>