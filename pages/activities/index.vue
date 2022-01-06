<template>
  <b-container class="main">

  <div class="main">
  <section id="activities" class="sectionPrimary">
      <div class="container">
        <h2 class="headingPrimary">活動内容</h2>
            <b-row class="Wrap_Link sectionPrimary flex-row-reverse" style="padding-bottom:0;padding-top:0;">

                <b-col v-for="activity in activities.contents" :key="activity.id" class="Link_In col-sm-6 col-12 col-md-3 align-self-start">
                    <div>
                    <img style="border-radius:3%"
                      :src="activity.image.url" alt="activity">
                    </div>
                    <span class="play_title">{{ activity.title }}</span><div>{{ activity.body }}</div>
                </b-col>
            </b-row>
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
    const activities = await $microcms.get({
      endpoint: `activities`,
    })
    return {
      activities,
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

  .Wrap_Link {
      display: flex;
      height: 100%;
      font-size: 16px;
      letter-spacing: -1px;
      padding-right: 20px;
      padding-left: 20px;
      justify-content:flex-end;
  }

  .play_title {
    font-size:1.2rem;
    font-weight: 1000;
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
