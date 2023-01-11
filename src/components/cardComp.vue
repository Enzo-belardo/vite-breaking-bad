<script>
import { store } from '../store.js'
export default{
    data() {
        return {
            store,
        }
    },
    
}

</script>

<template>
    <div class="col" v-for="card in store.cardList" >
        <div class="card ">
            <img :src="card.card_images[0].image_url"  class=“card-img-top” alt=““>
            <div class="card-body">
                <h5 class="card-title"> {{ card.name }}</h5>
                <p class="card-text">{{ card.archetype }}</p>
            </div>
        </div>
    </div>
</template>



<style lang="scss" scoped>
.card-body{
    height:130px;
}

</style>
