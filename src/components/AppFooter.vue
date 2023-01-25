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

    h1{
        font-size: 50px;
        font-weight: bold;
        color: $white;
        font-family: 'Source Serif Pro', serif;
    }

    .white-button{
        background-color: $white;
        color: $purple;
        width: fit-content;
        padding: 15px 40px;
        border-radius: 10px;
        font-size: 18px;
    }

</style>