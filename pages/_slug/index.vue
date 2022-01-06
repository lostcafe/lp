<template>
  <b-container class="main">
    <h1 class="title">{{ blogs.title }}</h1>
    <p class="ReleaseDate">
                  <time
                    :datetime="blogs.ReleaseDate"
                    v-text="$dateFns.format(new Date(blogs.ReleaseDate), 'yyyy.MM.dd')"
                  />
    </p>
    <div class="post" v-html="body"></div>
  </b-container>
</template>

<script>
export default {
  async asyncData({ $microcms, params }) {
    const blogs = await $microcms.get({
      endpoint: `blogs/${params.slug}`,
    })
    return {
      blogs,
    }
  },
}
</script>

