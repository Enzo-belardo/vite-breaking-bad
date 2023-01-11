<script>
import CardComp from './CardComp.vue';
import { store } from '../store.js'
import axios from 'axios';

export default{
    name: 'appMain',
    components : {
        CardComp,

    },
    data() {
        return {
            store,
            url: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0',

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
       <div class="container mt-4">
          <div class="row row-cols-1 row-cols-md-3 row-cols-lg-5 g-4">
              <CardComp v-for="n in 15"/>
           </div>
       </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

main{
    background-color: $main-color;
}


</style>
