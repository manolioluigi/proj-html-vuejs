<script>

    import { store } from '../store';
    import AppCarousel from './AppCarousel.vue';
    import AppCarouselLarge from './AppCarouselLarge.vue';
    import AppImageOverlay from './AppImageOverlay.vue';

    export default {

        name: 'AppMain',

        components: {
            AppCarousel,
            AppCarouselLarge,
            AppImageOverlay
        },

        data() {
            return {
                store,
                imageOverlay: [
                    {
                        url: '/src/assets/img/bakery-process-1.jpg',
                        title: 'Tell us what you have in mind',
                        number: '01',
                        desc: 'Cras consequat lectus vestibulum tortor pulvinar, quis euismod nisl varius. Ut eu laoreet ex. Aliquam erat volutpat. Nullam quis sagittis nibh. Morbi consectetur ultricies ante ac congue. Donec lorem erat, finibus in velit placerat, rutrum augue.',
                        descTitle: 'MANUAL INGREDIENTS SELECTION'
                    },
                    {
                        url: '/src/assets/img/bakery-process-2.jpg',
                        title: 'We Start Baking',
                        number: '02',
                        desc: 'Cras consequat lectus vestibulum tortor pulvinar, quis euismod nisl varius. Ut eu laoreet ex. Aliquam erat volutpat. Nullam quis sagittis nibh. Morbi consectetur ultricies ante ac congue. Donec lorem erat, finibus in velit placerat.',
                        descTitle: 'SWEET & DELICIOUS'
                    },
                    {
                        url: '/src/assets/img/bakery-process-3.jpg',
                        title: 'Delivered to your home',
                        number: '03',
                        desc: 'Cras consequat lectus vestibulum tortor pulvinar, quis euismod nisl varius. Ut eu laoreet ex. Aliquam erat volutpat. Nullam quis sagittis nibh. Morbi consectetur ultricies ante ac congue. Donec lorem erat, finibus in velit placerat, rutrum augue.',
                        descTitle: 'BAKED TO ORDER & GIFT WRAPPED'
                    }
                ]
            }
        },

    }

    
</script>

<template>
  
    <div class="container d-flex flex-column align-items-center">

        <!--prima riga-->

        <div class="row my-5">

            <div class="col-4">

                <p class="gray font-size-12">OUR PRODUCTS</p>
                <h1 class="my-4">All our delectable pastries are backed fresh in our Kitchen very morning, and are made with all-natural, all organic ingredients.</h1>
                <div class="purple-button font-size-14 my-5">Buy Avada Today</div>

            </div>

            <div class="col-8">

                <AppCarousel></AppCarousel>

            </div>

        </div>

        <!--seconda riga-->

        <div class="row">

            <div class="col-12 d-flex flex-column align-items-center my-5">

                <p class="gray font-size-12">CORPORATE & WEDDINGS</p>
                <h1 class="my-3">Baking Special Moments</h1>

            </div>

        </div>

        <!--terza riga-->

        <div class="row mb-5">

            <div class="col-12 d-flex justify-content-center">

                <div class="row d-flex justify-content-between">
                    <div class="col-6 padding-10 container-vertical-cards relative">
                        <img src="../assets/img/corporate-bg.jpg">
                        <img class="on-top" src="../assets/img/corporate-hover-bg.jpg">
                        <div class="more-on-top">
                            <span>International Bakery</span>
                            <h1 class="my-4">Corporate Events</h1>
                            <div class="purple-button">Explore more</div>
                        </div>
                    </div>
                    <div class="col-6 padding-10 container-vertical-cards relative">
                        <img src="../assets/img/wedding-bg.jpg">
                        <img class="on-top" src="../assets/img/wedding-hover-bg.jpg">
                        <div class="more-on-top">
                            <span>Private Dining Hall</span>
                            <h1 class="my-4">Weddings & Parties</h1>
                            <div class="purple-button">Explore more</div>
                        </div>
                    </div>
                </div>

            </div>

        </div>

        <!--quarta riga-->

        <div class="row my-5">

            <div class="col-3 text-center d-flex flex-column align-items-center">

                <h1 class="my-4">Find a freshly baked product perfect for you</h1>
                <span>Integer a nibh vitae ex porttitor rutrum et ut velit. Etiam ac felis at leo feugiat placerat. Sed ac nulla id orci tempor convallis sed.</span>
                <div class="purple-button font-size-14 my-4">Buy Avada Today</div>

            </div>

            <div class="col-9">

                <AppCarouselLarge></AppCarouselLarge>

            </div>

        </div>

        <!--quinta riga-->

        <div class="row">

            <div class="col-12">
                
                <AppImageOverlay class="my-5" :firstImage="this.imageOverlay[0]"></AppImageOverlay>
                
            </div>

        </div>

        <div>
            <AppImageOverlay :secondImage="this.imageOverlay[1]"></AppImageOverlay>
        </div>

    </div>

</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

    h1{
        font-size: 35px;
        font-weight: bold;
        color: $daisy-bush;
        font-family: 'Source Serif Pro', serif;
    }

    .purple-button{
        background-color: $purple;
        color: $white;
        width: fit-content;
        padding: 10px 25px;
        border-radius: 10px;
    }

    .container-vertical-cards{
        img{
            width: 100%;
            height: 700px;
            object-fit: cover;
        }
        &:hover .on-top{
            display: block;
        }
        &:hover .more-on-top{
            opacity: 1;
        }
    }
    
    .on-top{
        position: absolute;
        padding: 0 10px;
        top: 0;
        left: 0;
        z-index: 99;
        display: none;
    }

    .more-on-top{
        position: absolute;
        padding: 0 10px;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        z-index: 999;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: $white;
        font-size: 13px;
        opacity: 0;
        h1{
            color: $white;
        }
    }

    .padding-10{
        padding: 0 10px;
    }

</style>