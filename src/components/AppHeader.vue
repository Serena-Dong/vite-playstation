<script>
import { headerData } from '../data/data';

export default {
    name: 'AppHeader',
    data() {
        return {
            headerData
        }
    },
}
</script>

<template>
    <header>

        <!-- Logo SONY -->
        <div class="logo">
            <div class="container-sm">
                <div class="logo d-flex justify-content-end align-items-center">
                    <a href=""><img class="logo-header-img" src="./../assets/img/sony_logo.svg" alt=""></a>
                </div>
            </div>
        </div>

        <!-- Navbar -->
        <div class="navbar">
            <div class="container-sm">
                <div class="d-flex w-100 justify-content-between align-items-center">

                    <!-- Navbar Left -->
                    <div class="col-1 col-xxl-8 d-flex">
                        <!-- Logo -->
                        <a href=""><img class="logo-navbar-img pt-1" src="./../assets/img/play_logo.svg" alt="">
                        </a>
                        <!-- Nav-actions -->
                        <div class="nav-actions align-items-center">
                            <ul class="text-black d-flex align-items-center">
                                <li v-for="link in headerData.navbar">
                                    <a href="#">{{ link }} <i class="fa-solid fa-chevron-down text-secondary"></i></a>
                                </li>
                            </ul>
                        </div>
                    </div>

                    <!-- Navbar Right -->
                    <div class="col-2 col-lg-1 col-xxl-4">

                        <!-- Mobile Menù -->
                        <div class="bars">
                            <a href=""><i class="fa-bars fa-solid p-2 px-3 border border-grey rounded-3 fs-3"></i></a>
                        </div>

                        <!-- Desktop Menù -->
                        <div class="nav-actions align-items-center justify-content-end">
                            <ul class="d-flex align-items-center">
                                <li><a href="">My PlayStation <i class="fa-solid fa-chevron-down text-secondary"></i></a></li>
                                <li><a id="btn-login" href="" class="btn bg-black text-white  mb-0">Accedi</a></li>
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

    .logo{
        background-color: $ps-black;
        .logo {
            height: 40px;
        }
    }

    .navbar{
        background-color: $ps-white;

        &, .nav-actions{
            height: 80px;
        }
        
        .nav-actions ul>* {
            margin-left: 15px;
        }
        
        .nav-actions ul li>* {
            color: $ps-black;
        }

        .bars a {
            color: $ps-grey;
        }
    }


    .nav-actions {
        display: none;
    }
}
</style>
