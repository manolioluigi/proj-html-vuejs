<script>

    import { store } from '../store';

    export default {

        name: 'AppHeader',
        data() {
            return {
                store,
                scroll: 0,
                navbar: [
                    {
                        label:'HOME',
                        url: '#',
                        active: true
                    },
                    {
                        label:'SHOP',
                        url: '#',
                        active: false
                    },
                    {
                        label:'ABOUT',
                        url: '#',
                        active: false
                    },
                    {
                        label:'GALLERY',
                        url: '#',
                        active: false
                    },
                    {
                        label:'LOCATIONS',
                        url: '#',
                        active: false
                    },
                    {
                        label:'JOURNAL',
                        url: '#',
                        active: false
                    },
                    {
                        label:'CONTACT',
                        url: '#',
                        active: false
                    }
                ],

            }
        },

        methods: {
            handleScroll() {
            this.scroll = window.scrollY;
            },
        },

        mounted() {
            window.addEventListener('scroll', this.handleScroll);
        },

        beforeUnmount() {
            window.removeEventListener('scroll', this.handleScroll);
        },

    }
</script>

<template>
  
    <div class="container-fluid">

        <!--prima riga-->

        <div class="row">

            <div class="col-12 d-flex justify-content-center">

                <p class="purple my-2 font-size-14">Free International Shipping — 10% OFF SITE</p>

            </div>

        </div>
        
        <!--seconda riga-->

        <div class="row absolute font-size-12 purple d-flex justify-content-between px-3 py-2" :class="(this.scroll > 70 && this.scroll < 400) ? 'fixed' : ''">

            <div class="col-3 d-flex align-items-center">

                <img src="../assets/img/avada-bakery-logo-retina.png" alt="logo">

            </div>

            <div class="col-3 d-flex align-items-center justify-content-center">

                <ul class="d-flex mt-3 relative">

                    <li v-for="(item, index) in navbar" :key="index" class="mx-4">
                        <a class="purple" :href="item.url">{{ item.label }}</a>
                    </li>

                    <div class="underline"></div>

                </ul>
                

            </div>

            <div class="col-3 d-flex align-items-center justify-content-end">

                <a href="#" class="purple mx-3">ACCOUNT</a>
                <i class="fa-solid fa-cart-shopping"></i>

            </div>

        </div>

        <!--terza riga-->
        
        <div class="row jumbo">

            <div class="col-3 m-5">

                <p class="gray font-size-12">FRESH & TASTY BAKERY EVERY DAY</p>
                <h1>The Perfect Fresh Bread</h1>
                <p class="gray font-size-16">Cras consequat lectus vestibulum tortor pulvinar, quis euismod nisl varius. Aliquam erat volutpat. Nullam quis sagittis nibh ac nulla id orci tempor.</p>
                <div class="gray font-size-14 mt-5 mx-4">Explore our products</div>

            </div>

        </div>

    </div>

</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

    .purple{
        color: $purple;
    }

    .gray{
        color: $gray;
    }

    .font-size-14{
        font-size: 14px;
    }

    .font-size-16{
        font-size: 16px;
    }

    .font-size-12{
        font-size: 12px;
    }

    img{
        max-height: 9vh;
    }

    .relative{
        position: relative;
    }

    .absolute{
        position: absolute;
        z-index: 999;
    }

    .underline{
        width: 11%;
        height: 3px;
        background-color: $purple;
        position: absolute;
        bottom: -50%;
        left: 5%;
    }

    .jumbo{
        height: 80vh;
        padding-top: 10vh;
        background-image: url("../assets/img/hero-header-bakery.jpg");
        background-size: 150%;
        background-position: bottom;
        background-repeat: no-repeat;
        position: relative;

        h1{
            font-size: 50px;
            font-weight: bold;
            color: $daisy-bush;
            font-family: 'Source Serif Pro', serif;
        }
    }

    .fixed{
        position: fixed;
        top: 0;
        background-color: $white;
        z-index: 999;
    }

</style>