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
            card: [],
        }
    },
    methods:{
        getCard(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                // handle success
                console.log(response.data.data);
                this.card = response.data.data
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
        this.getCard();
    }
}
</script>

<template>
    <AppSearch/>
    <CardList :card="card"/>
</template>

<style lang="scss" scoped>

</style>
