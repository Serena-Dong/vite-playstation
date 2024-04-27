<script>
import Button from './Button.vue';

export default {
    name: 'Jumbotron',
    components: { Button },
    props: {
        jumbotron: Array
    }
}
</script>
<template>
    <section class="jumbotron">
        <div class="container-sm">
            <div class="row">
                <div class="col-12 col-md-6 col-lg-4">
                    <div class="jumbotron-content">
                        <img :src="jumbotron.logo" alt="">
                        <p>{{ jumbotron.title }}</p>
                        <p>{{ jumbotron.description }}</p>
                        <Button :button="jumbotron.button"></Button>
                    </div>
                </div>
            </div>
        </div>
    </section>

</template>
<style scoped lang="scss">
@import "./../../assets/scss/partials/variables";

.jumbotron {
    height: 600px;
    background-image: $jumbotron-image;
    background-position: top center;
    background-size: cover;
    background-repeat: no-repeat;

    display: flex;
    align-items: center;
    color: white;
    padding: 3rem;

    margin: 0 !important;

    .jumbotron-content {
        p {
            margin-bottom: 1.5rem;
        }

        img {
            margin-bottom: 1.25rem;
            width: 50%;
        }
    }
}
</style>