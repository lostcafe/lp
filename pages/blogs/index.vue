<template>
  <b-container class="main">

  <div class="main">




  <section id="news" class="sectionPrimary">

  <div style="margin-bottom:20px">
    <b-card-group deck>

      <b-card style="border:0px;">
        <template>
        <h2 class="headingPrimary">ニュース</h2>
        </template>
        <b-card-text>

  <div class="common">
    <li v-for="blogs in blogs.contents" :key="blogs.id">
      <nuxt-link :to="`/${blogs.id}`">
        {{ blogs.title }}
      </nuxt-link>
      <span class="date">
                  <time
                    :datetime="blogs.ReleaseDate"
                    v-text="
                      $dateFns.format(new Date(blogs.ReleaseDate), 'yyyy.MM.dd')
                    "
                  />
      </span>
    </li>
  </div>


        </b-card-text>
      </b-card>
    </b-card-group>
                          <p class="button-area">
          <nuxt-link to="./" class="buttonPrimary">もどる</nuxt-link>
        </p>
  </div>

  </section>






  </div>

  </b-container>
</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const blogs = await $microcms.get({
      endpoint: `blogs`,
    })
    return {
      blogs, 
    }
  },
}
</script>

<style scoped>
  .sectionPrimary {
    padding: 3em 0;
  }

  .headingPrimary {
    font-size: 2.5rem;
    font-weight: 700;
    text-transform: capitalize;
    text-align: center;
    margin-bottom: 1em;
  }

.common {
  display: block;
}

.common li:nth-of-type(n+6) {
  display: none;
}

.common a {
  display: block;
  width: 70%;
  float: left;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  font-size: 1.2rem;
  color: #198754;
  font-weight: 500;
}

.common span {
  width: 25%;
  float: right;
  text-align: right;
  color: #8c8c8c;
  white-space: nowrap;
  font-size: 1.2rem;
}

@media (max-width: 480px) {
    .common a {
      font-size: 0.9rem;
    }

    .common span {
      font-size: 0.9rem;
    }

}

.common_center {
    text-align: center;
}

.common_title {
    font-weight:1000;
    font-size: 1.3rem;
    margin-bottom: 10px;
    color: #198754;
}

ul, li {
    list-style: none;
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 0.9rem;
    vertical-align: baseline;
    list-style-type: none;
    }

  .button-area {
    text-align: center;
    margin-top: 2em;
  }

  .buttonPrimary {
      color: #010101;
      display: inline-block;
      font-family: Ubuntu,sans-serif;
      font-size: 1.125rem;
      font-weight: 700;
      text-transform: capitalize;
      text-align: center;
      text-indent: -1em;
      line-height: 56px;
      padding: 0 1em;
      border: 2px solid;
      border-radius: 4px;
      min-width: 230px;
      position: relative;
  }

  img {
    object-fit: cover;
    width: 100%;
    height: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
  }
</style>
