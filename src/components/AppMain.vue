<script>
import AppSearch from './AppSearch.vue';
import CardList from './CardList.vue';
import axios from 'axios';

export default {
    components:{
        AppSearch,
        CardList
    },
    data(){
        return{
            cards: [],
            
        }
    },
    methods:{
        getCards(archetypeName){
            let urlAPI = ''

            if (typeof archetypeName === 'undefined') {
                urlAPI = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0'
            } else {
                urlAPI = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=' + archetypeName
            }

            axios.get(urlAPI)
            .then((response) => {
                // handle success
                console.log(response.data.data);
                this.cards = response.data.data
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });
        },
        selectedArchetype(archetype){
            console.log(archetype)
            this.getCards(archetype)
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <main>
        <AppSearch @selected="selectedArchetype"/>
        <CardList :cards="cards"/>
    </main>
</template>

<style lang="scss" scoped>

main{
    background-color: #C58635;
    height: 100vh;
    padding: 2rem;
}

</style>
