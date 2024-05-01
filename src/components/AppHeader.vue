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

            <!-- Navbar -->
            <div class="navbar container-sm">

                <!-- Navbar Left -->
                <div class="navbar-left col-1 col-xxl-8 d-flex">
                    <!-- Logo -->
                    <a href="">
                        <img class="navbar-logo" :src="'/img/' + header.navbar.image" alt="">
                    </a>
                    <!-- Nav-actions -->
                    <div class="nav-actions align-items-center">

                        <div v-for="group in header.navbar.groups" class="dropdown d-flex align-items-center">
                            <div class="dropbtn">{{ group.name }} <i
                                    class="fa-solid fa-chevron-down text-secondary"></i>
                            </div>
                            <div class="dropdown-content">
                                <a v-for="link in group.links" href="#">{{ link.name }}</a>
                            </div>
                        </div>
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
                                <Button :button="header.navbar.button"></Button>
                            </li>
                            <li><a href=""><i class="fa-solid fa-magnifying-glass"></i></a></li>
                        </ul>
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
        // height: 70px;


        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            height: 70px;


            .navbar-logo {
                margin-right: 1rem;
            }

            .nav-actions {

                ul>* {
                    margin-left: 15px;
                }

                ul li>* {
                    color: $ps-black;
                }

                .dropdown {
                    position: relative;
                    display: inline-block;
                    cursor: pointer;

                    margin-right: 1rem;

                    &:hover .dropdown-content {
                        display: block !important;
                    }

                    &:hover .dropbtn,
                    &:hover .fa-chevron-down {
                        color: $ps-blue !important;
                    }

                    .dropbtn {
                        padding: 1rem 0;

                    }

                    .dropdown-content {
                        display: none;
                        position: absolute;
                        background-color: $ps-white;
                        min-width: 300px;
                        z-index: 1;
                        top: 100%;

                        a {
                            color: black;
                            padding: 10px 20px;
                            text-decoration: none;
                            display: block;

                            &:hover {
                                background-color: $ps-blue;
                                color: $ps-white;

                            }
                        }
                    }

                    .dropdown:hover .dropdown-content {
                        display: block;
                    }

                }

            }



            #bars a {
                color: $ps-grey;

                .fa-bars {
                    padding: 0.5rem 1rem;
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
