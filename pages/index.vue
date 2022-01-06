<template>

<b-container fluid="xl">
  <div class="large-img" style="margin-bottom:20px;padding-right:0px;">
    <b-carousel
      id="carousel-fade"
      style="text-shadow: 0px 0px 2px #000"
      fade
      img-width="1024"
      img-height="200"
    >
      <b-carousel-slide
        img-src="https://kosodate.hiraharahoiku.com/img/s06.jpg"
      ></b-carousel-slide>
      <b-carousel-slide
        img-src="https://kosodate.hiraharahoiku.com/img/s05.jpg"
      ></b-carousel-slide>
      <b-carousel-slide
        img-src="https://kosodate.hiraharahoiku.com/img/s01.jpg"
      ></b-carousel-slide>
    </b-carousel>
  </div>



    <MyButtons>
      </MyButtons>




    <div style="margin-bottom:20px;">
    <b-card border-variant="success">
        <div class="common_title common_center">お知らせS</div>
        <b-card-text>
          <li v-for="notice in notices.contents" :key="notice.id">
        {{ notice.Notice_body }}
      <br><span class="date" style="float:right">
                  <time
                    :datetime="notice.Notice_UpdateDate"
                    v-text="$dateFns.format(new Date(notice.Notice_UpdateDate), 'yyyy.MM.dd')"
                  />
      </span>
    </li>
        </b-card-text>
    </b-card>
    </div>





  <div class="main">
    <section id="about" class="sectionPrimary">
      <div class="container">
        <h2 class="headingPrimary">利用案内</h2>
        <div class="profile">
          <b-row class="profile_top">
            <b-col class="profile__image w-100 col-lg-5 col-12">
              <b-img width="260" height="260" fluid-grow src="https://higashihiroshima-digital-kodomoto.com/wp-content/uploads/2021/10/IMG_7271.jpg" alt="your name" />
            </b-col>

            <b-col class="profile__text">
              <p class="profile__name">
                東広島子育て支援センター 
              </p>
              <dl class="profile__item">
                <dt class="profile__title">■住所</dt>
                <dd>　東広島市西条町御薗宇0000-0</dd>
              </dl>
              <dl class="profile__item">
                <dt class="profile__title">■電話番号</dt>
                <dd>　082-00X-0X22</dd>
              </dl>
              <dl class="profile__item">
                <dt class="profile__title">■開放日時</dt>
                <dd>　月曜日~金曜日 10時~15時</dd>
              </dl>
            </b-col>
          </b-row>
          <b-row class="profile_bottom">育児相談、園庭や室内での遊び、リズムあそび、ふれあい遊び、絵本コーナー、親子遠足や親子クッキングを行っております。豊かな自然に囲まれた保育所を開放し、親子でのびのびと遊んでいただきます。<br />いろいろな人との出会いをとおし楽しく子育てしていきましょう。
          </b-row>
        </div>
      </div>
    </section>
  </div>





  <div class="main">
  <section id="activities" class="sectionPrimary">
      <div class="container">
        <h2 class="headingPrimary">活動内容</h2>
            <b-row class="Wrap_Link sectionPrimary" style="padding-bottom:0;padding-top:0;">

                <b-col v-for="activity in activities.contents" :key="activity.id" class="Link_In col-sm-6 col-12 col-md-3 align-self-start">
                    <div>
                    <img
                      :src="activity.image.url" alt="のびのびタイム">
                    </div>
                    <span class="play_title">{{ activity.title }}</span><div>{{ activity.body }}</div>
                </b-col>
                
            </b-row>
    </div>

  </section>
  </div>





  <div style="margin-bottom:20px">
    <b-card-group deck>

      <b-card header-tag="header" footer-tag="footer" class="rounded">
        <template #header>
          <h6 class="mb-0">ニュース</h6>
        </template>
        <b-card-text>

  <div class="common">
    <li v-for="blogs in blogs.contents" :key="blogs.id">
      <nuxt-link :to="`/${blogs.id}`">
        {{ blogs.title }}
      </nuxt-link>
      <span class="date ">
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

      <b-card title="title" header-tag="header" footer-tag="footer">
        <template #header>
          <h6 class="mb-0">行事日程</h6>
        </template>
        <b-card-text>Header and footers using slots.</b-card-text>
        <b-button href="#" variant="primary">Go somewhere</b-button>
      </b-card>

    </b-card-group>
  </div>













</b-container>



</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const blogs = await $microcms.get({
      endpoint: 'blogs',
    })

    const notices = await $microcms.get({
      endpoint: 'notices',
    })

    const activities = await $microcms.get({
      endpoint: 'activities',
    })

    return {
      blogs,
      notices,
      activities,
    }
  },
}
</script>

<style scoped>
.Wrapper {
    padding: 0px;
}

.Wrap_Link {
    display: flex;
    height: 100%;
    font-size: 16px;
    letter-spacing: -1px;
    padding-right: 20px;
    padding-left: 20px;
}

.Link_In {
    padding-left: 5px;
    padding-right: 5px;
    padding-top: 15px;
    padding-bottom: 15px;
    align-self:center;
}

.Link_In a div {
    padding-bottom: 10px;
}

.Link_In a {
    color: #fff;
}


@media (max-width: 480px) {
    .Link_In {
        padding-top: 10px;
        padding-bottom: 10px;
    }
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
}

.common span {
  width: 25%;
  float: right;
  text-align: right;
  color: #8c8c8c;
  white-space: nowrap;
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

.play_title {
  font-size:1.2rem;
  font-weight: 1000;
}

  p {
      display: block;
      margin-block-start: 1em;
      margin-block-end: 1em;
      margin-inline-start: 0px;
      margin-inline-end: 0px;
  }

  html {
      box-sizing: border-box;
      -webkit-text-size-adjust: 100%;
      word-break: normal;
      -moz-tab-size: 4;
      -o-tab-size: 4;
      tab-size: 4;
  }

  .profile_bottom {padding: 15px;}

  .sectionPrimary {
    padding: 3em 0;
}

  @media screen and (min-width: 768px) {
  .profile__name {
      font-size: 1.75rem;
      margin-bottom: 0.857em;}
  }

  .profile__name {
      font-size: 1.5rem;
      font-weight: 700;
      margin-bottom: 0.5em;
  }

  .profile__message {
    white-space: pre-wrap;
  }

  *, :after, :before {
      box-sizing: inherit;
  }

  section {
    display: block;
  }

  .headingPrimary {
    font-family: Ubuntu,sans-serif;
    font-size: 2.5rem;
    font-weight: 700;
    text-transform: capitalize;
    text-align: center;
    margin-bottom: 1em;
  }

  h2 {font-weight: 700;}

img {
  object-fit: cover;
  width: 100%;
  height: 100%;
  border-radius:3%;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>
