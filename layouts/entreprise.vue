<template>
    <v-app dark>
        <!---- Navigation ---->
        <navigation-component> </navigation-component>
        <!------ Content -------->
        <v-main >
            <nuxt />
        </v-main>
        <!------ Footer --------->
        <footer1-component></footer1-component>
    </v-app>
</template>

<script>
import Footer1Component from '@/components/Footer1Component.vue';
import NavigationComponent from '@/components/NavigationComponent.vue';
    export default {
        components: {
            Footer1Component,
            NavigationComponent,
        },
    }
</script>

<style scoped>

</style>