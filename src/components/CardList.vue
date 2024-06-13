<script>
import SingleCard from './SingleCard.vue';

export default {
    components:{
        SingleCard
    },
    data(){
        return{
            
        }
    },
    props:{
        cards:{
            type: Array,
            required: true
        }
    }
}
</script>

<template>
    <section class="cards-list container">
        <div class="row">
            <h2 class="col-12">
                found {{ cards.length }} cards
            </h2>
            <div class="col-12">
                <div>
                    <SingleCard v-for="card in cards" :key="card.index"/>
                </div>
            </div>
        </div>
    </section>
    
</template>

<style scoped>

</style>