<script>
export default {
    name: 'Jumbotron'
}
</script>
<template>
    <section class="jumbotron text-white p-5 d-flex align-items-end">
        <div class="container-sm">
            <div class="row">
                <div class="col-12 col-md-6 col-lg-4">
                    <div class="text">
                        <img class="img-fluid mb-3" src="./../../assets/img/returnal-hero-banner-logo.png" alt="">
                        <p class="title mb-4">Rompi il cerchio</p>
                        <p class="mb-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis ipsa, totam
                            saepe veniam eum sunt omnis, in illum quisquam minus consequuntur libero id repellat?
                            Placeat.</p>
                        <a class="btn btn-red bg-danger">
                            Acquista ora
                        </a>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>
<style scoped lang="scss">
.jumbotron {
    height: 600px;

    background-image: url('./../../assets/img/jumbo-bg.png');
    background-position: top center;
    background-size: cover;
    background-repeat: no-repeat;
}
</style>