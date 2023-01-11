<script>
import CardComp from './CardComp.vue';
import { store } from '../store.js'

export default{
    name: 'appMain',
    components : {
        CardComp,

    },
    data() {
        return {
            store,
            url: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0',

        }
    },
    methods: {
        getCard() {
            axios.get(this.url)
            .then((response) => {
                 console.log(response.data.data);
                this.store.cardList = response.data.data;
            })
            .catch(function (error) {
                console.log(error);
            })
        }
    },
    created() {
        this.getCard();
    }
}
</script>

<template>
    <main>
       <div class="wrapper">
          <article v-for="card in store.cardList" class="">
             <div class="card">
                <img :src="card.card_images[0].image_url" :alt="card.name">
                <div class="description">
                    <p>{{ card.name }}</p>
                    <p>{{ card.archetype }}</p>
                </div>
             </div>
          </article>
       </div>
    </main>
</template>

<style lang="scss">
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

.wrapper{
    background-color: blue;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}


</style>
