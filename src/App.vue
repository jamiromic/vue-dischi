<template>
  <div id="app">
    <HeaderComponent @selectedGenre="selectedOption"/>
    <MainComponent :selectedGenre="genreMusical"/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';


export default {
  name: 'App',
  data() {
    return {
      genreMusical: 'All'
    }
  },
  components: {
    HeaderComponent,
    MainComponent
},
methods: {
  selectedOption(data) {
    this.genreMusical = data
    
  }

}
}
</script>

<style lang="scss">
@import "./styles/index.scss";
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
</style>
