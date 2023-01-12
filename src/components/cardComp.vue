<script>
import { store } from '../store.js'
export default{
    name: 'cardComp',
    data() {
        return {
            store,
        }
    },
    
}

</script>

<template>
    <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
       <option selected>Open this select menu</option>
       <option value="1">Alien</option>
       <option value="2">Laval</option>
       <option value="3">Vylon</option>
       <option value="1">Inzektor</option>
       <option value="2">Umi</option>
       <option value="3">Gusto</option>
    </select>
    <div class="col" v-for="card in store.cardList" >
        <div class="card ">
            <img :src="card.card_images[0].image_url"  class=“card-img-top” alt=''>
            <div class="card-body">
                <h5 class="card-title"> {{ card.name }}</h5>
                <p class="card-text">{{ card.archetype }}</p>
            </div>
        </div>
    </div>
    <div class="col-12">
        <p class="navbar-brand  text-danger">found {{ store.cardList.length }} cards</p>
    </div>
</template>



<style lang="scss" scoped>
.card-body{
    height:100px;
    h5{
        font-size: 1rem;
    }
}

</style>
