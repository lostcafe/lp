<template>
    <div style="margin-bottom:20px;">
    <b-card border-variant="success">
        <div class="notice_title notice_center">お知らせ</div>
        <b-card-text>

        </b-card-text>
    </b-card>
    </div>
</template>

<script>
  import Notice from '@/components/Notice'
  export default {
components: {
  Notice,
    }
}
</script>

<style scoped>
.notice_center {
    text-align: center;
}

.notice_title {
    font-weight:1000;
    font-size: 1.3rem;
    margin-bottom: 10px;
    color: #198754;
}
</style>