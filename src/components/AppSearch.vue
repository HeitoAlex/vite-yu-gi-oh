<script>
import axios from 'axios';

export default {
    data(){
        return{
            categories: []
        }
    },
    methods:{
        getArchetype(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                // handle success
                console.log(response.data);
                this.categories = response.data
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
        this.getArchetype();
    }
}
</script>

<template>
    <div class="select-container">
        <select>
            <option v-for="archetype in categories" @click="$emit('selected', archetype.archetype_name)">
                {{ archetype.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped>

div.select-container{
    margin-bottom: 2rem;
}
</style>