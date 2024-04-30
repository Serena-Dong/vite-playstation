<script>
import Button from './Button.vue'
export default {
    name: 'products',
    components: {
        Button
    },
    props: {
        products: Object
    },
    data() {
        return {
            currentImageIndex: 0,

        }
    },
    computed: {
        currentImage() {
            return this.products[this.currentImageIndex];
        }
    },
    methods: {
        prevImage() {
            this.currentImageIndex = (this.currentImageIndex - 1 + this.products.length) % this.products.length;
        },
        nextImage() {
            this.currentImageIndex = (this.currentImageIndex + 1) % this.products.length;
        },
        setCurrentImage(index) {
            this.currentImageIndex = index;
        }
    }
}

</script>

<template>
    <section class="products">
        <div class="container-sm">

            <!-- Intro -->
            <div class="products-header text-center mb-5">
                <p class="text-blue text-uppercase m-0">play has not limits</p>
                <p class="title">Ecco la PlayStaion 5</p>
                <p>Tuffati in nuove possibilità di gioco completamente inaspettate</p>
            </div>

            <!-- Carousel -->
            <div class="carousel">
                <div class="carousel-text col-12 col-lg-5 ">
                    <p class="title">{{ currentImage.title }}</p>
                    <p>{{ currentImage.text }}</p>
                    <div class="d-flex gap-2">
                        <Button v-for="button in currentImage.buttons" :button="button"></Button>
                    </div>
                </div>

                <div class="carousel-img col-12 col-lg-6 ">
                    <img :src="'img/' + currentImage.img" alt="" class="img-fluid">
                </div>
            </div>

            <!-- Thumbnail -->
            <div class="thumbnail-products">
                <div v-for="(image, index) in products" :key="index" class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid border-blue" :class="{ 'thumb-active': index === currentImageIndex }"
                        :src="'/img/' + image.img" alt="" @click="setCurrentImage(index)">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.products {

    .carousel {
        display: flex;
        justify-content: space-between;

        .carousel-text {
            display: flex;
            flex-direction: column;
            justify-content: center;

            .title {
                font-size: 2rem;
            }

            &>* {
                margin-bottom: 2rem;
            }
        }
    }

    .thumbnail-products {
        display: flex;
        flex-wrap: wrap;

        img:hover {
            border-bottom: 2px solid $ps-blue;
            transform: scale(1.02);

            transition: 0.2s border-bottom;
        }
    }

    /* Animations */
    .thumb-active {
        border-bottom: 2px solid $ps-blue;
    }
}
</style>