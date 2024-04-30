<script>
import Button from './Button.vue';

export default {
    name: 'Games',
    components: {
        Button
    },
    props: {
        games: Array
    },
    data() {
        return {
            currentImageIndex: 0,
            autoplayInterval: null, // Interval for autoplay
            autoplayDelay: 5000, // Autoplay delay in milliseconds
            isAutoplayEnabled: true, // Flag to enable/disable autoplay
        };
    },
    computed: {
        currentImage() {
            return this.games[this.currentImageIndex];
        }
    },
    methods: {
        prevImage() {
            this.currentImageIndex = (this.currentImageIndex - 1 + this.games.length) % this.games.length;
        },
        nextImage() {
            this.currentImageIndex = (this.currentImageIndex + 1) % this.games.length;
            if (!this.showText) {
            }
        },
        setCurrentImage(index) {
            this.currentImageIndex = index;
        },
        toggleAutoplay() {
            this.isAutoplayEnabled = !this.isAutoplayEnabled;
            if (this.isAutoplayEnabled) {
                // Start autoplay
                this.autoplayInterval = setInterval(this.nextImage, this.autoplayDelay);

            } else {
                // Stop autoplay
                clearInterval(this.autoplayInterval);
            }
        }
    },
    mounted() {
        // Start autoplay when component is mounted
        if (this.isAutoplayEnabled) {
            this.autoplayInterval = setInterval(this.nextImage, this.autoplayDelay);
        }
    },
    beforeDestroy() {
        // Clear autoplay interval to prevent memory leaks
        clearInterval(this.autoplayInterval);
    }
};
</script>


<template>
    <section class="games">

        <!-- Carousel -->
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

        <!-- Thumbnail -->
        <div class="thumbnail-container">
            <div id="thumbnail-gallery">
                <div v-for="(image, index) in games" :key="index" class="img-container">
                    <img :class="{ 'thumb-active': index === currentImageIndex }" :src="'/img/' + image.img" alt=""
                        @click="setCurrentImage(index)">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.games {
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
                // opacity: 0;
                transition: opacity 0.5s ease-in-out;
            }

            // &.show-text>* {
            //     opacity: 1 !important;
            // }
        }

        /* Arrows */
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

                width: 205px;
                height: 120px;
                display: flex;
                justify-content: center;

                margin: 1.5rem 0.5rem;

                img {
                    width: 100%;
                    object-fit: cover;
                    border-radius: 1rem;
                    margin: 0 0.5rem;

                    cursor: pointer;
                    filter: blur(0.7px);
                    filter: grayscale(0.5);
                    transition: filter .0.5s;
                    transition: transform .5s;

                    &:hover {
                        transform: scale(1.06);
                        box-shadow: 1px 1px 20px black;

                        filter: blur(0) !important;
                    }
                }
            }
        }
    }

    /* Animations */
    .active {
        display: block !important;
    }

    .thumb-active {
        box-shadow: 1px 1px 20px black;
        transform: scale(1.07);
        filter: blur(0) !important;
        border: 4px solid $ps-blue;
        padding: 3px;
    }
}
</style>