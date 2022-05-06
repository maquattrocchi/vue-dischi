<template>
  <div id="app">
    <header-component/>
    <main>
        <grid-component/>
    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import GridComponent from './components/GridComponent.vue';

export default {
    name: 'App',
    components: {
        HeaderComponent,
        GridComponent,
    }
}
</script>

<style lang="scss">
    @import './style/general';
</style>
