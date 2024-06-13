<script>

export default {
    data(){
        return{
            
        }
    },
    props:{
        card:{
            type: Object,
            required:true
        }
    }
}
</script>

<template>
    <div class="card">
        <img :src="card" class="card-img-top" alt="">
        <div class="card-body">
            <h4>

            </h4>
            <p>

            </p>
        </div>
    </div>
</template>

<style scoped>

</style>