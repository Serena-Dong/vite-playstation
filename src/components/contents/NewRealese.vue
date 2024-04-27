<script>
export default {
    name: 'NewRealese',
    props: {
        newRealese: Array
    }
}
</script>

<template>
    <div class="new-realese">
        <div class="container-sm">

            <div class="new-realese-header">
                <h3 class="mb-3">{{ newRealese.title }}</h3>
                <h4>{{ newRealese.description }}</h4>
            </div>


            <div class="new-realise-main">
                <div class="row">
                    <div v-for="game in newRealese.games" class="col-6 col-md-4 col-lg-2 mb-4">
                        <img class="img-fluid rounded-5 mb-2" :src="game.img" alt="">
                        <p class="fw-semibold">{{ game.title }}</p>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
@import "./../../assets/scss/partials/variables";

.new-realese {
    color: $ps-white;
    background-color: $ps-grey-dark;

    .new-realese-header {
        padding: 2rem 0;
    }

    .new-realise-main {
        padding: 0 0 2rem 0;
    }
}
</style>