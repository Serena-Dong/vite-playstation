<script>
export default {
    name: 'Button',
    props: {
        button: Object
    }
}
</script>

<template>
    <div class="button">
        <a :class="'btn-' + [button.color]" class="btn" href="">{{ button.text }}</a>
    </div>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.button {
    .btn-blue {
        background-color: $ps-blue;
        color: $ps-white;
    }

    .btn-white {
        background-color: $ps-white;
        color: $ps-blue;
    }

    .btn-red {
        background-color: $ps-red;
        color: $ps-white;
    }

    .btn-black {
        background-color: $ps-black;
        color: $ps-white;
    }
}
</style>