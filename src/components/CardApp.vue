<script>
    export default {
        name: 'CardApp',
        props: {
            thumb: String,
            series: String

        }
            
    }
</script>


<template>
    <div class="card">
        <div class="image-container">
            <img :src="thumb" :alt="series">
        </div>
        <h5>{{series}}</h5>
    </div>
</template>

<style lang="scss" scoped>

    .card {
        width: calc(100% / 6 - 2rem);
        

        img {
            display: block;
            width: 100%;
            aspect-ratio: 1/1;
            object-fit: cover;
        }

        h5 {
            text-align: start;
            margin-top: 1rem;
        }
        
    }
    
</style>