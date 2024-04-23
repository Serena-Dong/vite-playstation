<script>
import { footerData } from '../data/data';

export default {
    name: 'AppFooter',
    data() {
        return {
            footerData
        }
    },
}
</script>
<template>
    <footer class="bg-blue text-white">
        <div class="container-sm pt-5">

            <div class="footer-top ">
                <div class="row">

                    <div class="col-12 col-lg-6 pt-5">
                        <img class="ps d-block mb-5" src="./img/ps-footer.svg" alt="">
                        <img class="globe" src="./img/language-globe.svg" alt="">
                        <span class="px-2"> Country / Region: Italy </span>

                    </div>
                    <div class="col-12 col-lg-6 pt-5">
                        <div class="row" id="links">
                            <div class="col-12 col-lg-4 ">
                                <ul>
                                    <li v-for="link in footerData.about"><a href="#">{{ link }}</a></li>

                                </ul>
                            </div>
                            <div class="col-12 col-lg-4 ">
                                <ul>
                                    <li v-for="link in footerData.support"><a href="#">{{ link }}</a></li>
                                </ul>
                            </div>
                            <div class="col-12 col-lg-4 ">
                                <ul>
                                    <li v-for="link in footerData.resources"><a href="#">{{ link }}</a></li>

                                </ul>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
            <div class="footer-bottom py-5">
                <div class="row">
                    <div class="col-12 col-lg-6">
                        <img class="sie mb-2" src="./../assets/img/sie-logo.svg" alt="">
                        <div class="text small">
                            <p>Website ©2022 Sony Interactive Entertainment Europe Limited. Tutti i contenuti, nomi dei
                                giochi, nomi commerciali e/o di abbigliamento, marchi registrati, grafica e immagini
                                associati sono marchi registrati e/o materiale protetto da copyright dei rispettivi
                                proprietari. Tutti i diritti riservati. <a href=""><u>Maggiori info</u></a></p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>
<style scoped lang="scss">
@import "./../assets/scss/partials/variables";

footer {
    background-color: $ps-blue;
}

#links .col-12 ul li {
    padding-bottom: 0.5rem;
}
</style>