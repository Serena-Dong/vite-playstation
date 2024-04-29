<script>
export default {
    name: 'card',
    props: {
        img: String,
        title: String,
        description: String,
        button: String
    }
}
</script>

<template>
    <img class="img-fluid" :src="'/img/' + img" alt="">
    <p class="title mb-4">{{ title }}</p>
    <p class="mb-3">{{ description }}</p>
    <a class="btn btn-blue bg-blue " href="">{{ button }}</a>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.bg-blue {
    background-color: $ps-blue;
}
</style>