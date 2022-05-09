<template>
    <div class="input-group mb-3">
        <label class="input-group-text" :for="info">Search by {{info}}</label>
        <select class="form-select" :name="info" :id="info" v-model="searchBy" @change="searchDisc">
            <option value="">All</option>
            <option :value="item" v-for="item in list" :key="item">{{item}}</option>
        </select>
    </div>
</template>

<script>
    export default {
        name: 'SearchComponent',
        props: ['list', 'info'],
        data(){
            return {
                searchBy: '',
            }
        },
        methods:{
            searchDisc(){
                this.$emit('search', this.searchBy)
            }
        }
    }
</script>

<style lang="scss" scoped>
    @import '../style/vars';

    .input-group-text {
        font-size: 1.3rem;
        font-weight: bold;
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