<template>
  <b-container class="main">
    <h1 class="title">{{ blog.title }}</h1>
    <p class="ReleaseDate">
                  <time
                    :datetime="blog.ReleaseDate"
                    v-text="$dateFns.format(new Date(blog.ReleaseDate), 'yyyy.MM.dd')"
                  />
    </p>
    <div class="post" v-html="body"></div>
  </b-container>
</template>

<script>
export default {
  async asyncData({ $microcms, params }) {
    const blog = await $microcms.get({
      endpoint: `blog/${params.slug}`,
    })
    return {
      blog,
    }
  },
}
</script>

