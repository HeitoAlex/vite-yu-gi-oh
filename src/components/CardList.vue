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
    <section>
        <div id="founded">
            <h2>
                Founded {{ cards.length }} cards
            </h2>
        </div>
        <div id="card-list">
                <SingleCard v-for="card in cards" :key="card.id" :card="card"/>
        </div>
    </section>
</template>

<style lang="scss" scoped>

section{
    width: 1200px;
    margin: 0 auto;
    background-color: white;
    padding: 3rem;
}

#founded{
    width: 100%;
    color: white;
    background-color: #212529;
    padding: .5rem;
}

#card-list{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}



</style>