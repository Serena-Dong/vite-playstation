<script>
import Jumbotron from './contents/Jumbotron.vue';
import Banner from './contents/Banner.vue';
import Container from './contents/Container.vue';
import NewRealese from './contents/NewRealese.vue';
import { createApp } from 'vue';
import { mainData } from '../data/data';


export default {
    name: 'AppMain',
    components: { Jumbotron, Banner, Container, NewRealese },
    data() {
        return {
            mainData
        }
    }
}

</script>
<template>
    <main>
        <Jumbotron :jumbotron="mainData.jumbotron"></Jumbotron>
        <NewRealese :newRealese="mainData.newRealese"></NewRealese>
        <Container v-for="container in mainData.containers" :order="container.order" :title="container.title"
            :intro="container.intro" :cards="container.cards" :images="container.images"></Container>

        <Banner v-for="banner in mainData.banners" :order="banner.order" :logo="banner.logo"
            :description="banner.description" :button="banner.button" :bgColor="banner.bgColor" :img="banner.img"
            :color="banner.color"></Banner>

    </main>
</template>
<style scoped lang="scss">
main {
    display: flex;
    flex-direction: column;
}
</style>