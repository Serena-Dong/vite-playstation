<script>
import Button from './Button.vue'

export default {
    name: 'Products',
    components: {
        Button
    },
    props: {
        products: Array
    }
}
</script>

<template>
    <section class="products bg-white">
        <div class="container-sm">
            <div class="text-center mb-5">
                <p class="text-blue text-uppercase m-0">play has not limits</p>
                <p class="title">Ecco la PlayStaion 5</p>
                <p>Tuffati in nuove possibilità di gioco completamente inaspettate</p>
            </div>


            <div class="row">
                <div class="col-12 col-lg-6 d-flex align-items-center ">
                    <div class="text ">
                        <p class=" title"></p>
                        <p>Sperimenta la nuova generazione di incredibili giochi PlayStation.</p>
                        <a class="btn btn-blue bg-blue " href="">Maggiori informazioni
                        </a>
                    </div>
                </div>
                <div class="col-12 col-lg-6 ">
                    <img class="img-fluid" src="/img/playstation-5-thumb.png" alt="">
                </div>
            </div>
            <div class="thumbnail-products row flex-wrap ">
                <div class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid border-blue" src="./img/playstation-5-thumb.png" alt="">
                </div>
                <div class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid rounded-3" src="./img/joypad-thumb.png" alt="">
                </div>
                <div class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid rounded-3" src="./img/headset-thumb.png" alt="">
                </div>
                <div class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid rounded-3" src="./img/remote-thumb.png" alt="">
                </div>
                <div class="col-4 col-lg-2 text-center ">
                    <img class="img-fluid rounded-3" src="./img/camera-thumb.jpg" alt="">
                </div>

            </div>
        </div>
    </section>
</template>

<style></style>