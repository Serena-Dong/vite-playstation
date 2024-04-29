<script>
import Card from './Card.vue';
import Button from './Button.vue';

export default {
    name: 'Container',
    components: { Card, Button },
    props: {
        order: String,
        title: String,
        intro: String,
        cards: Array,
        images: Array
    },
    data() {
        return {
        }
    }
}
</script>

<template>
    <section :class="order">
        <div class="container-sm">

            <!-- Text -->
            <div class="text-center py-3">
                <p class="fs-1">{{ title }}</p>
                <p>{{ intro }}
                </p>
            </div>

            <!-- Content -->

            <!-- CARD -->
            <div v-if="cards" id="card" class="row">
                <div v-for="card in cards" class="col-12 col-md-4 mb-4">
                    <div class="img-container">
                        <img class="img-fluid" :src="'/img/' + card.img" alt="">
                    </div>
                    <p class="title mb-4">{{ card.title }}</p>
                    <p class="mb-4">{{ card.description }}</p>
                    <Button :button="card.button"></Button>
                </div>
            </div>

            <!-- IMAGE -->
            <div v-if="images" class="row">
                <div v-for="image in images" class="col">
                    <img class=" img-fluid" :src="'/img/' + image.path" alt="">
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped></style>