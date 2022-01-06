<template>
  <v-app dark>
    <MyNavbar>
    </MyNavbar>
    <MyCarousel>
    </MyCarousel>
    <nuxt />
    <MyFooter>
    </MyFooter>
  </v-app>
</template>

<script>
  export default {}
</script>

<style scoped>
.large-img {
  margin: 0 -15px;
  width: calc(100% + 30px);
}
</style>