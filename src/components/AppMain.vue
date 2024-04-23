<script>
import Jumbotron from './contents/Jumbotron.vue';
import Social from './contents/Social.vue';
import { createApp } from 'vue';


export default {
    name: 'AppMain',
    components: { Jumbotron, Social }
}

</script>
<template>
    <main>
        <Jumbotron></Jumbotron>
        <Social></Social>
    </main>
</template>
<style scoped lang="scss"></style>