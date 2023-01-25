<script>

    import { store } from '../store';

    export default {

        name: 'AppFooter',
        data() {
            return {
                store,
            }
        },

    }
</script>

<template>
    <div class="container-fluid no-padding">

        <!--prima riga-->

        <div class="row my-5 width-full no-margin-sides">

            <div class="col-12 no-padding">
                
                <div class="call-to-action">
                    <img src="../assets/img/call-to-action-bg.jpg">
                    <div class="content">
                        <span class="gray font-size-12">TRY OUR SEASONAL PRODUCTS</span>
                        <h1 class="my-4">Order for pick-up or delivery to your home</h1>
                        <div class="white-button my-4">Shop Now</div>
                    </div>
                </div>
                

            </div>

        </div>

        <!--seconda riga-->

        <div class="row mb-5">

            <div class="col-7 d-flex flex-column justify-content-center align-items-start px-5 mb-5">

                <img src="../assets/img/avada-bakery-logo.png" alt="">
                <div class="my-3 navbar d-flex flex-column">
                    <div class="d-flex justify-content-between width-full">
                        <a href="#">Shop</a>
                        <a href="#">About</a>
                        <a href="#">Gallery</a>
                        <a href="#">Locations</a>
                        <a href="#">Journal</a>
                    </div>
                    <div class="d-flex justify-content-between width-full shifted">
                        <a href="#">Contact</a>
                        <a href="#">Orders</a>
                    </div>
                </div>
                <span class="my-2 darkgray font-size-12">© Copyright 2019 | Avada Theme by ThemeFusion | All Rights Reserved | Powered by WordPress</span>

            </div>

            <div class="col-5 text-center">

                <h3 class="purple">Subscribe to our Newsletter</h3>
                <div class="email mt-3">
                    <input type="email" class="form-control" aria-describedby="emailHelp" placeholder="Enter email addess*">
                    <div class="purple-button">Subscribe</div>
                </div>
                <div class="social">
                    <div><i class="fa-brands fa-instagram"></i></div>
                    <div class=" mx-2"><i class="fa-brands fa-twitter"></i></div>
                    <div><i class="fa-brands fa-facebook"></i></div>
                    <div class=" mx-2"><i class="fa-brands fa-pinterest"></i></div>
                    <div><i class="fa-brands fa-youtube"></i></div>
                </div>

            </div>

        </div>

    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

    .call-to-action{
        width: 100%;
        height: 50vh;
        position: relative;
        img{
            width: 100%;
            height: 50vh;
            object-fit: cover;
            object-position: middle;
        }
        .content{
            padding: 5%;
            width: 50vw;
            display: flex;
            flex-direction: column;
            position: absolute;
            top: 0;
        }
    }

    a{
        color: $purple;
    }

    h1{
        font-size: 50px;
        font-weight: bold;
        color: $white;
        font-family: 'Source Serif Pro', serif;
    }

    h3{
        font-size: 25px;
        font-weight: bold;
        font-family: 'Source Serif Pro', serif;
    }

    .white-button{
        background-color: $white;
        color: $purple;
        width: fit-content;
        padding: 15px 40px;
        border-radius: 10px;
        font-size: 18px;
        cursor: pointer;
        &:hover{
            color: $white;
            background-color: $purple;
        }
    }

    .purple-button{
        background-color: $purple;
        color: $white;
        width: fit-content;
        padding: 10px 25px;
        border-radius: 10px;
        cursor: pointer;
        &:hover{
            color: $purple;
            background-color: $white;
        }
    }

    .col-7 img{
        width: 150px;
    }

    .email{
        display: flex;
        input{
            width: 60%;
        }
    }

    .social{
        display: flex;
        justify-content: end;
        margin: 10% 13% 0 0;
        font-size: 20px;
        color: $purple;
        div{
            width: 35px;
            height: 35px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 10px;
        }
        div:hover{
            background-color: $gray;
        }
    }

    .navbar{
        width: 80%;
        .shifted{
            margin-top: 10px;
            margin-left: 40px;
        }
    }

</style>