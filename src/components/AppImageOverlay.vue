<script>
    export default {
        name: 'AppImageOverlay',
        data() {
            return {

            }
        },
        props: {
            firstImage: Object,
            secondImage: Object
        },
        
    }
</script>

<template>

    <div>
        
        <div class="my-image-container" v-if="firstImage">
            <img :src="firstImage.url">
            <div class="content">
                <div class="d-flex justify-content-between">
                    <div class="title">
                        <h1>{{ firstImage.title }}</h1>
                    </div>
                    <span class="number">{{ firstImage.number }}</span>
                </div>
                <div class="d-flex justify-content-end">
                    <div class="desc">
                        <span class="my-2">{{ firstImage.descTitle }}</span>
                        <p>{{ firstImage.desc }}</p>
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

    .my-image-container{
        width: 100%;
        height: 80vh;
        position: relative;
        img{
            max-width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: left;
        }

        .content{
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: absolute;
            top: 0;
            padding: 40px 60px;
            background-color: rgba(86, 50, 139, 0.507);
            color: $white;
            .number{
                font-size: 100px;
            }
        }
        .title{
            width: 50%;
            h1{
                font-size: 55px;
                font-family: 'Source Serif Pro', serif;
            }
        }
        .desc{
            width: 30%;
            span{
                font-size: 13px;
            }
            p{
                font-size: 16px;
            }
        }
    }

</style>