<template>
    <b-container fluid="xl">
        <b-navbar toggleable="lg" type="dark">
            <b-navbar-brand href="/">
                <span class="title">東広島子育て支援センター</span>
            </b-navbar-brand>
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
            </b-collapse>
        </b-navbar>
    </b-container>
</template>

<script>
  import MyNavbar from '@/components/MyNavbar'
  export default {
components: {
  MyNavbar,
    }
}
</script>

<style scoped>
    .title {font-weight: 700;color: #198754;}
    .navbar {padding: 0.5em 0em;/*padding: 0.5em 1.5em;box-shadow: 0 0.2rem 0.2rem 0 rgb(0 0 0 / 25%);*/}
</style>