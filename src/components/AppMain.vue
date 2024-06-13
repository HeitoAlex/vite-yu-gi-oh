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
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
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
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <main>
        <AppSearch/>
        <CardList :cards="cards"/>
    </main>
</template>

<style lang="scss" scoped>

main{
    background-color: #C58635;
    height: 100vh;
}

</style>
