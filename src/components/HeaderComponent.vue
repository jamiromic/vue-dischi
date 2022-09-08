<template>
  <header>
    <img src="https://cdn-icons-png.flaticon.com/512/2111/2111624.png" alt="Spotify Icon">
    <div class="wrapper_select">
      <h2>Scegli il tuo genere :</h2>
      <select v-model="selectedGenre" @click="$emit('selectedGenre', selectedGenre)" id="genre_musical_selected">
      <option value="All" selected>All</option>
      <option value="Rock">Rock</option>
      <option value="Metal">Metal</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
    </select>
    </div>
    
  </header>
</template>

<script>
export default {
  data() {
    return {
      selectedGenre: 'All'
    }
  }
 
}
</script>


<style scoped lang="scss">

  header {

    background-color: #2E3A46;
    padding: 0.85rem 1.70rem;
    display: flex;

    img {
      width: 50px;
    }

    .wrapper_select {

      margin-left: 30px;


      select {
        margin-left: 150px;
      }



    }


    
  }

</style>
