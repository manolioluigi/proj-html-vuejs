<script>
    export default {
        name: 'AppCarousel',
        data() {
            return {
                carouselItem1: '0',
                carouselItem2: '1',
                carouselArray: [
                    {
                        url: '/src/assets/img/choco-chip-cookies.jpg',
                        title: 'Choco chip cookies',
                        category: 'Cookies',
                        type: 'Pastries',
                        minPrice: '$18.00',
                        maxPrice: '$32.00'
                    },
                    {
                        url: '/src/assets/img/strawberry-jam-cookies.jpg',
                        title: 'Strawberry jam cookies',
                        category: 'Cookies',
                        type: 'Pastries',
                        minPrice: '$36.00',
                        maxPrice: '$60.00'
                    },
                    {
                        url: '/src/assets/img/cookies-with-ice-cream.jpg',
                        title: 'Cookies with ice cream',
                        category: 'Cookies',
                        type: 'Pastries',
                        minPrice: '$18.00',
                        maxPrice: '$34.00'
                    },
                    {
                        url: '/src/assets/img/home-bread.jpg',
                        title: 'Homemade bread',
                        category: 'Breads',
                        type: 'Pastries',
                        minPrice: '$26.00',
                        maxPrice: '$68.00'
                    }
                ]
            }
        },
        methods: {
            carouselIncrease(){
                this.carouselItem1++
                if(this.carouselItem1 > this.carouselArray.length - 1){
                    this.carouselItem1 = 0;
                }
                this.carouselItem2++
                if(this.carouselItem2 > this.carouselArray.length - 1){
                    this.carouselItem2 = 0;
                }
            },
            carouselDecrease(){
                this.carouselItem1--
                if(this.carouselItem1 < 0){
                    this.carouselItem1 = this.carouselArray.length -1;
                }
                this.carouselItem2--
                if(this.carouselItem2 < 0){
                    this.carouselItem2 = this.carouselArray.length -1;
                }
            }
        }
    }
</script>

<template>
  
    <div class="my-carousel">

        <div class="my-carousel-item">
            <img :src="carouselArray[carouselItem1].url">
            <div class="text">
                <h3>{{ carouselArray[carouselItem1].title }}</h3>
                <span>{{ carouselArray[carouselItem1].category }}, {{ carouselArray[carouselItem1].type }}</span>
                <p>{{ carouselArray[carouselItem1].minPrice }}, {{ carouselArray[carouselItem1].maxPrice }}</p>
            </div>
        </div>
        <div class="my-carousel-item">
            <img :src="carouselArray[carouselItem2].url">
            <div class="text">
                <h3>{{ carouselArray[carouselItem2].title }}</h3>
                <span>{{ carouselArray[carouselItem2].category }}, {{ carouselArray[carouselItem2].type }}</span>
                <p>{{ carouselArray[carouselItem2].minPrice }}, {{ carouselArray[carouselItem2].maxPrice }}</p>
            </div>
        </div>

        <div class="arrow-button-left" @click="carouselDecrease">&lt;</div>
        <div class="arrow-button-right" @click="carouselIncrease">&gt;</div>

    </div>

</template>

<style lang="scss" scoped>

    @use '../styles/partials/variables.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

    .my-carousel{
        display: flex;
        justify-content: space-between;
        position: relative;
    }
    .my-carousel-item{
        display: flex;
        justify-content: center;
        position: relative;
        max-width: 48%;

        &:hover .text{
            opacity: 1;
            background-color: rgba(86, 50, 139, 0.507);
        }

        img{
            max-width: 100%;
        }
        .text{
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            text-align: center;
            padding-top: 50%;
            color: $white;
            opacity: 0;
            transition: opacity .5s ease-in-out;
            h3{
                font-size: 25px;
            }
        }
    }

    .arrow-button-left{
        color: $white;
        background-color: $purple;
        max-height: fit-content;
        max-width: fit-content;
        position: absolute;
        left: 0;
        top: 45%;
        padding: 30px 15px;
        opacity: 0.5;
        &:hover{
            opacity: 1;
        }
        cursor: pointer;
    }

    .arrow-button-right{
        color: $white;
        background-color: $purple;
        max-height: fit-content;
        max-width: fit-content;
        position: absolute;
        right: 0;
        top: 45%;
        padding: 30px 15px;
        opacity: 0.5;
        &:hover{
            opacity: 1;
        }
        cursor: pointer;
    }

</style>