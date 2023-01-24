<script>

    import { store } from '../store';
    import AppCarousel from './AppCarousel.vue';

    export default {

        name: 'AppMain',

        components: {
            AppCarousel,
        },

        data() {
            return {
                store,
            }
        },

    }
</script>

<template>
  
    <div class="container">

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

        <div class="row">

            <div class="col-12">

                <div class="d-flex justify-content-between">
                    <div>img</div>
                    <div>img</div>
                </div>

            </div>

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

</style>