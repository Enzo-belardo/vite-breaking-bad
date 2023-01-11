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
    <main class="">
        
       <div class="container bg-light d-flex flex-wrap justify-content-center">
          <div class="bg-dark text-light w-100 d-flex">
              <h3 class="text-center p-2">
                 found {{ store.cardList.length }} cards
              </h3>
          </div>

           <div class="row row-cols-3 row-cols-md-5 g-3">
               <div class="col-3 col-ms-5" v-for="card in store.cardList" >
                  <div class="card">
                     <img :src="card.card_images[0].image_url" :alt="card.name" class="img-fluid card-img-top">
                     <div class="card-body">
                         <h4>{{ card.name }}</h4>
                         <p>{{ card.archetype }}</p>
                     </div>
                  </div>
               </div>
           </div>
       </div>
    </main>
</template>

<style lang="scss">
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

main{
    background-color: $main-color;

}
.card-body{
    height: 100px;
    h4{
        font-size: 1rem;
    }
}

</style>
