<script>
    export default {
        name: 'AppCarousel',
        data() {
            return {
                carouselItem1: '0',
                carouselItem2: '1',
                carouselItem3: '2',
                carouselItem4: '3',
                carouselArray: [
                    {
                        url: '/src/assets/img/choco-chip-cookies.jpg',
                        title: 'Choco Chip Cookies',
                        minPrice: '$18.00',
                        maxPrice: '$32.00'
                    },
                    {
                        url: '/src/assets/img/strawberry-jam-cookies.jpg',
                        title: 'Strawberry Jam Cookies',
                        minPrice: '$36.00',
                        maxPrice: '$60.00'
                    },
                    {
                        url: '/src/assets/img/strawberry-donut.jpg',
                        title: 'Strawberry Donut',
                        minPrice: '$24.00',
                        maxPrice: '$48.00'
                    },
                    {
                        url: '/src/assets/img/perfect-macarons.jpg',
                        title: 'Perfect Macarons',
                        minPrice: '$32.00',
                        maxPrice: '$56.00'
                    },
                    {
                        url: '/src/assets/img/premium-bread.jpg',
                        title: 'Premium Bread',
                        minPrice: '$32.00',
                        maxPrice: '$68.00'
                    },
                    {
                        url: '/src/assets/img/cherry-cake.jpg',
                        title: 'Cake with Cherry Topping',
                        minPrice: '$80.00',
                        maxPrice: '$99.00'
                    },
                    {
                        url: '/src/assets/img/cookies-with-ice-cream.jpg',
                        title: 'Cookies with ice cream',
                        minPrice: '$18.00',
                        maxPrice: '$34.00'
                    },
                    {
                        url: '/src/assets/img/blackberry-stuffed-bread.jpg',
                        title: 'Blackberry Stuffed Bread',
                        minPrice: '$22.00',
                        maxPrice: '$46.00'
                    },
                    {
                        url: '/src/assets/img/glazed-pancake-with-lemon.jpg',
                        title: 'Glazed Bread with Fruits',
                        minPrice: '$36.00',
                        maxPrice: '$24.00'
                    },
                    {
                        url: '/src/assets/img/small-cupcake.jpg',
                        title: 'Chocolate Cupcake',
                        minPrice: '$26.00',
                        maxPrice: '$68.00'
                    },
                    {
                        url: '/src/assets/img/home-bread.jpg',
                        title: 'Homemade bread',
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
                this.carouselItem3++
                if(this.carouselItem3 > this.carouselArray.length - 1){
                    this.carouselItem3 = 0;
                }
                this.carouselItem4++
                if(this.carouselItem4 > this.carouselArray.length - 1){
                    this.carouselItem4 = 0;
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
                this.carouselItem3--
                if(this.carouselItem3 < 0){
                    this.carouselItem3 = this.carouselArray.length -1;
                }
                this.carouselItem4--
                if(this.carouselItem4 < 0){
                    this.carouselItem4 = this.carouselArray.length -1;
                }
            }
        }
    }
</script>

<template>
  
    <div class="my-carousel">

        <div class="my-carousel-item d-flex flex-column">
            <img :src="carouselArray[carouselItem1].url">
            <div class="text">
                <p>SELECT OPTIONS /</p>
                <p>QUICK VIEW</p>
            </div>
            <div class="under-text">
                <h3>{{ carouselArray[carouselItem1].title }}</h3>
                <p>{{ carouselArray[carouselItem1].minPrice }}, {{ carouselArray[carouselItem1].maxPrice }}</p>
            </div>
        </div>
        <div class="my-carousel-item d-flex flex-column">
            <img :src="carouselArray[carouselItem2].url">
            <div class="text">
                <p>SELECT OPTIONS /</p>
                <p>QUICK VIEW</p>
            </div>
            <div class="under-text">
                <h3>{{ carouselArray[carouselItem2].title }}</h3>
                <p>{{ carouselArray[carouselItem2].minPrice }}, {{ carouselArray[carouselItem2].maxPrice }}</p>
            </div>
        </div>
        <div class="my-carousel-item d-flex flex-column">
            <img :src="carouselArray[carouselItem3].url">
            <div class="text">
                <p>SELECT OPTIONS /</p>
                <p>QUICK VIEW</p>
            </div>
            <div class="under-text">
                <h3>{{ carouselArray[carouselItem3].title }}</h3>
                <p>{{ carouselArray[carouselItem3].minPrice }}, {{ carouselArray[carouselItem3].maxPrice }}</p>
            </div>
        </div>
        <div class="my-carousel-item d-flex flex-column">
            <img :src="carouselArray[carouselItem4].url">
            <div class="text">
                <p>SELECT OPTIONS /</p>
                <p>QUICK VIEW</p>
            </div>
            <div class="under-text">
                <h3>{{ carouselArray[carouselItem4].title }}</h3>
                <p>{{ carouselArray[carouselItem4].minPrice }}, {{ carouselArray[carouselItem4].maxPrice }}</p>
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
        max-width: 24%;

        &:hover .text{
            display: block;
            background-color: rgba(86, 50, 139, 0.507);
        }

        img{
            max-width: 100%;
        }
        .text{
            width: 100%;
            height: 70%;
            position: absolute;
            top: 0;
            text-align: center;
            padding-top: 50%;
            color: $white;
            display: none;
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

    .under-text{
        text-align: center;
        color: $purple;
        font-size: 13px;
        height: 30%;
        padding: 20px 5px;
        h3{
            font-size: 22px;
            font-weight: bold;
        }
    }

</style>