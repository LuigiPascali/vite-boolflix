<script>

    export default {
        name: "FooterComponent",
        data() {
            return {

            }
        },
        methods: {

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

    <footer>
        FOOTER
    </footer>

</template>

<style lang="scss" scoped>

    @use "../assets/scss/partials/variables.scss" as *;

    footer {
        padding: 40px;
        text-align: center;
    }

</style>
  