<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';


export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
}
}
</script>

<style lang="scss">
@import "./styles/index.scss";
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
</style>
