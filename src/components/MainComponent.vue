<template>
    <main>
        <div class="card_wrapper">       
                <div v-for="(item,i) in filteredGenre" :key="i" class="col">
                    <CardComponent :info="item"/>
                
            </div>
        </div>

    </main>
</template>

<script>
    import axios from 'axios';
    import CardComponent from './CardComponent.vue';

    export default {
        name: 'MainComponent',
        props: {
            selectedGenre: String,
                
        },

        data() {
            return {
                listAlbums: []
            };
        },
        computed: {
            filteredGenre() {

                return this.listAlbums.filter((element) => {

                    const genre = element.genre
                    const inputGenre = this.selectedGenre

                    if (genre === inputGenre || inputGenre === 'All'){

                        return true
                        
                    }

                    return false

                })
            }
               
        },

        components: {
            CardComponent
        },
        created() {
            axios
                .get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((res) => {
                    
                    this.listAlbums = res.data.response;
                })
                .catch((err) => {
                    console.log('Error:', err);
                })
        }
        
    }

</script>

<style lang="scss" scoped>

    main {
        background-color: #1E2D3B;

        .card_wrapper {
            max-width: 1400px;
            margin: 0 auto;
            padding-top: 6rem;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.5rem 2.5rem;


            .col {
                width: 220px;
                height: 380px;
                background-color: #2E3A46;
                display: flex;
                flex-direction: column;
                align-items: center;
                padding: 1.5rem 1.5rem 3rem 1.5rem;

                    .card {
                        width: auto;
                        height: auto;

                            
                    }
            }
   
            


        }
    
    }

    

</style>