<script>
import Button from './Button.vue'
export default {
    name: 'Carousel',
    components: {
        Button
    },
    props: {
        carousel: Array
    },
    data() {
        return {
            currentImageIndex: 0,

        }
    },
    computed: {
        currentImage() {
            return this.carousel[this.currentImageIndex];
        }
    },
    methods: {
        prevImage() {
            this.currentImageIndex = (this.currentImageIndex - 1 + this.carousel.length) % this.carousel.length;
        },
        nextImage() {
            this.currentImageIndex = (this.currentImageIndex + 1) % this.carousel.length;
        },
        setCurrentImage(index) {
            this.currentImageIndex = index;
        }
    }
}

</script>

<template>
    <section class="carousel">
        <div class="carousel-container">
            <!-- <div @click="prevImage" id="prev" class="fa-solid fa-arrow-left arrow"></div> -->
            <div class="carousel-gallery">
                <img :src="'img/' + currentImage.img" alt="" class="active">
            </div>
            <div class="carousel-text col-12 col-md-4">
                <div class="game-logo col-12">
                    <img :src="'img/' + currentImage.logo" alt="">
                </div>
                <p>{{ currentImage.text }}</p>
                <Button :button="currentImage.button"></Button>
            </div>

            <!-- <i @click="nextImage" id="next" class="fa-solid fa-arrow-right arrow"></i> -->
        </div>
        <div class="thumbnail-container">
            <div id="thumbnail-gallery">
                <div v-for="(image, index) in carousel" :key="index" class="img-container">
                    <img :class="{ 'thumb-active': index === currentImageIndex }" :src="'/img/' + image.img" alt=""
                        @click="setCurrentImage(index)">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.carousel {
    height: 100vh;

    .carousel-container {
        width: 100%;
        height: 70%;
        position: relative;

        .carousel-gallery {
            width: 100%;
            height: 100%;

            img {
                width: 100%;
                height: 100%;
                object-fit: cover;

                display: none;
            }
        }

        .carousel-text {
            position: absolute;
            top: 0%;
            padding: 3rem;
            height: 70vh;

            display: flex;
            flex-direction: column;
            justify-content: end;

            img {
                width: 100%;
            }

            &>* {
                color: $ps-white;
                margin-bottom: 2rem;
            }
        }

        .arrow {
            color: $ps-white;
            background-color: #000000;
            border-radius: 3rem;

            padding: 1rem;
            cursor: pointer;

            position: absolute;
            top: 50%;
            transform: translateY(-50%);

            &:hover {
                background-color: #4f4f4f;
            }

        }

        #prev {
            right: calc(100% - 100px);
        }

        #next {
            left: calc(100% - 100px);
        }
    }

    .thumbnail-container {
        width: 100%;
        height: 20%;

        #thumbnail-gallery {
            display: flex;
            justify-content: center;
            flex-wrap: nowrap;

            .img-container {

                width: 180px;
                height: 90px;
                display: flex;
                justify-content: center;

                margin: 1.5rem 0.5rem;

                img {
                    width: 100%;
                    height: 100%;
                    object-fit: cover;
                    border-radius: 1rem;

                    margin: 0 0.5rem;

                    cursor: pointer;
                    transition: transform .2s;
                    transition: filter .0.5s;

                    &:hover {
                        transform: scale(1.1);
                        box-shadow: 1px 1px 20px black;
                    }
                }
            }
        }
    }

    .active {
        display: block !important;
    }

    .thumb-active {
        box-shadow: 1px 1px 20px black;
        transform: scale(1.1);
    }
}
</style>