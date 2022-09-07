<template>
    <div class="card">
        <img class="card_img" 
        :src="info.poster" :alt="info.author">
        <div class="card_body">
            <h2 class="card_title">{{ info.title }}</h2>
            <p class="card_author">{{ info.author }}</p>
            <p class="card_album_year">{{ info.year }}</p>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'CardComponent',
        props: {
            info: Object,
        },
        
    }
</script>

<style lang="scss" scoped>

    .card_body {

        text-align: center;
        color: #7B7673;
        

        .card_title {
        color: #FFFAF0;
        text-transform: uppercase;
        font-weight: 500;
        padding: 1rem 0;
        }

        .card_author {
            font-size: 1.25rem;
        
        
        }


    }

    

</style>