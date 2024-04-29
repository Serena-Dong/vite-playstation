<script>
import Button from './Button.vue';

export default {
    name: 'Banner',
    components: { Button },
    props: {
        order: String,
        logo: String,
        description: String,
        button: Object,
        img: String,
        bgColor: String,
        color: String
    }
}
</script>

<template>
    <!-- Color of the banner -->
    <section class="banner" :class="[bgColor, order]">
        <div class="container-sm">
            <div class="row align-items-center">

                <!-- Banner Text -->
                <div class="banner-text col-12 col-lg-6">
                    <div class="text py-5">
                        <img :src="'/img/' + logo" alt="">
                        <p :class="color">{{ description }}</p>
                        <Button :button="button"></Button>
                    </div>
                </div>

                <!-- Banner Img -->
                <div class="banner-img col-lg-6 img-none">
                    <img class="img-fluid" :src="'/img/' + img" alt="">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.banner {
    .banner-text {
        img {
            width: 50%;
        }

        p {
            padding: 3rem 0;
            margin-bottom: 0;
        }
    }
}
</style>