<template>
    <img :src="getLogo()">
</template>
<script>

export default {
    methods: {
        getLogo() {
            return "impii_logo_black.png" ;
        }
    }
}

</script>
