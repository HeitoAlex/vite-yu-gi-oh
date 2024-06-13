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
    <article>
        <img :src="card.card_images[0].image_url" alt="">
        <div id="text-card">
            <h4>
                {{ card.name }}
            </h4>
            <p>
                {{ card.archetype }}
            </p>
        </div>
    </article>
</template>

<style lang="scss" scoped>

article{
    width: calc((100% / 5) - 1rem);

        img{
        width: 100%;
        }

        #text-card{
            background-color: #C58635;
            text-align: center;
            padding: 1rem;
            margin-bottom: 1rem;

                h4{
                    text-transform: uppercase;
                    color: white;
                    margin-bottom: 1rem;
                }
        }


}


</style>