<script>

    export default {
        name: "HeaderComponent",
        data() {
            return {

            }
        },
        methods: {
            // funzione per le immagini:
            getImagePath: function(image){
                return new URL (image, import.meta.url).href;
            }
        },
        components: {
            //dichiarazione
        },
        props:{
            //utilizzo per file padre
        },
    }

</script>

<template>

    <header>
        HEADER
    </header>

</template>

<style lang="scss" scoped>

    @use "../assets/scss/partials/variables.scss" as *;

    header {
        padding: 40px;
        text-align: center;
    }

</style>