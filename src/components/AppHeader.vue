<script>
import { headerData } from '../data/data';
import Button from './contents/Button.vue';

export default {
    name: 'AppHeader',
    components: { Button },
    data() {
        return {
            header: headerData
        }
    },
}
</script>

<template>
    <header>

        <!-- Header Top -->
        <div class="header-top">
            <div class="container-sm">
                <div class="logo d-flex justify-content-end align-items-center">
                    <a href=""><img class="logo-header-img" :src="'/img/' + header.headerTop.image" alt=""></a>
                </div>
            </div>
        </div>

        <!-- Header Bottom -->
        <div class="header-bottom">
            <div class="container-sm">
                <!-- Navbar -->
                <div class="navbar d-flex w-100 justify-content-between align-items-center">

                    <!-- Navbar Left -->
                    <div class="navbar-left col-1 col-xxl-8 d-flex">
                        <!-- Logo -->
                        <a href="">
                            <img class="navbar-logo pt-1" :src="'/img/' + header.navbar.image" alt="">
                        </a>
                        <!-- Nav-actions -->
                        <div class="nav-actions align-items-center">
                            <ul class="text-black d-flex align-items-center">
                                <li v-for="link in header.navbar.links">
                                    <a :href="link.url">{{ link.name }} <i
                                            class="fa-solid fa-chevron-down text-secondary"></i></a>
                                </li>
                            </ul>
                        </div>
                    </div>

                    <!-- Navbar Right -->
                    <div class="navbar-right col-2 col-lg-1 col-xxl-4">

                        <!-- Mobile Menù -->
                        <div id="bars">
                            <a href=""><i class="fa-bars fa-solid p-2 px-3 border border-grey rounded-3 fs-3"></i></a>
                        </div>

                        <!-- Desktop Menù -->
                        <div class="nav-actions align-items-center justify-content-end">
                            <ul class="d-flex align-items-center">
                                <li>
                                    <a href="">
                                        My PlayStation
                                        <i class="fa-solid fa-chevron-down text-secondary"></i>
                                    </a>
                                </li>
                                <li>
                                    <Button :button="header.navbar.buttons"></Button>
                                </li>
                                <li><a href=""><i class="fa-solid fa-magnifying-glass"></i></a></li>
                            </ul>
                        </div>
                    </div>

                </div>
            </div>


        </div>
    </header>
</template>

<style scoped lang="scss">
@import "./../assets/scss/partials/variables";

header {
    position: sticky;
    top: 0;

    z-index: 99999;

    .header-top {
        background-color: $ps-black;

        .logo-header-img {
            height: 40px;
        }
    }

    .header-bottom {
        background-color: $ps-white;

        &,
        .nav-actions {
            height: 80px;
        }

        .navbar {
            .nav-actions ul>* {
                margin-left: 15px;
            }

            .nav-actions ul li>* {
                color: $ps-black;
            }

            #bars a {
                color: $ps-grey;

                .fa-bars {
                    padding: 0.5rme 1rem;
                    border: 1px solid $ps-grey;
                    border-radius: 0.5rem;
                    font-size: 1.75rem;
                }
            }
        }
    }


    .nav-actions {
        display: none;
    }
}
</style>
