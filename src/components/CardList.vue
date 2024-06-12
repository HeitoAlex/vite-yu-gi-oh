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
        card:{
            type: Array;
            required: true
        }
    }
}
</script>

<template>
    <SingleCard/>
</template>

<style scoped>

</style>