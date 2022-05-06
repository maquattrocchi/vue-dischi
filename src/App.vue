<template>
  <div id="app">
    <header-component/>
    <main>

    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent
  }
}
</script>

<style lang="scss">
    @import './style/general';
    //@import './style/general';
    #app {
        height: 100vh;
        
        main{
            height: calc(100% - 70px);
            background-color: $bg-color;
        }
    }
</style>
