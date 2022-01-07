<template>
  <footer class="footer">
    <p class="copyright">
      <small>©️2021 DY All Rights Reserved.</small>
    </p>
  </footer>
</template>

<script>
  import MyFooter from '@/components/MyFooter'
  export default {
components: {
  MyFooter,
    }
}
</script>

<style scoped>
.footer {
  padding: 1em 0;
  border-top:1px solid #35495e;
  text-align:center;
  font-size:16px;
  color:#41b883;
  margin:200px 0 0 0;
} 

.copyright {
  text-align: center;
}
</style>