<template>
  <v-main>
    <section>
      <!-- src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg" -->
      <v-parallax
        src="https://images.pexels.com/photos/1089438/pexels-photo-1089438.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
        height="500"
      >
        <v-row>
          <v-col class="align-self-center">
            <div class="font-weight-bold text-h6">
              Hola, I'm
              <span class="primary--text text--lighten-2">WebbLu</span>
            </div>
            <div class="font-weight-bold text-h3 my-3">PHP Web developer</div>

            <div
              class="font-weight-bold text-h4 mb-2"
              style="text-shadow: 3px 2px #000000"
            >
              You're Awesome!
            </div>
            <div class="font-weight-bold text-h5">
              May I Cooperate With You?
            </div>
          </v-col>
          <v-col class="d-flex align-end justify-center">
            <v-img
              class="justify-self-end"
              src="./../static/you-thumb-up.png"
              max-width="520"
            ></v-img>
          </v-col>
        </v-row>
        <!-- src="http://res.hpoi.net.cn/gk/cover/n/2015/02/a67d87bd0eba453b864f5daf1dce5fa5.jpg?date=1464613555000" -->
      </v-parallax>
    </section>
    <!-- About -->
    <section id="about">
      <v-container class="mt-5">
        <h1>About</h1>
        <v-row class="mt-1">
          <v-col >
            <p class="text-justify">
              索引走過的痕跡；<br />
              人與動物區別，在於思想、工具的使用、有價值觀所權衡。<br />
              透過工具組合各種元素成為 WebbLu 索引頁！<br />
              本頁索引四散各處的筆記，網誌以及 Github 專案，<br />
              若有任何寶貴的意見，您可以發送到
              <v-btn
                color="secondary"
                x-small
                href="mailto:'u.master.o.twn+landing@gmail.com'"
                >電子郵箱</v-btn
              >
            </p>
          </v-col>
          <v-col>
            <v-form ref="form">
              <v-text-field
                name="nickname"
                label="Nickname"
              ></v-text-field>
              <v-text-field
                name="email"
                label="E-Mail"
              ></v-text-field>
              <v-text-field
                name="message"
                label="Message"
              ></v-text-field>
              <v-btn class="mr-4 justify-left" color="primary" type="submit" disabled>submit</v-btn>
            </v-form>
          </v-col>
        </v-row>
        <div class="d-flex">
          <v-divider width="3px" class="ma-5"></v-divider>
          <v-btn color="blue" class="ma-1" text icon
            ><v-icon large>mdi-linkedin</v-icon>
          </v-btn>
          <v-btn color="black" class="ma-1" text icon
            ><v-icon large>mdi-github</v-icon>
          </v-btn>
          <v-btn color="blue lighten-2" class="ma-1" text icon
            ><v-icon large>mdi-twitter</v-icon>
          </v-btn>
          <v-divider class="ma-5"></v-divider>
        </div>
      </v-container>
    </section>
    <!-- <v-divider class="ma-5"></v-divider> -->
    <!-- Project -->
    <section id="project">
      <v-container grid-list-xs class="mt-5">
        <h1>Gist & Repo</h1>
        <v-row
          v-for="i in Math.ceil(projects.length / 4)"
          :key="i"
          class="mt-1"
        >
          <v-col v-for="j in 4" :key="j">
            <v-card shaped>
              <v-card-title primary-title>
                Card {{ 4 * (i - 1) + j }}
              </v-card-title>
              <v-card-subtitle> subtitle </v-card-subtitle>
              <v-card-text>
                Greyhound divisively hello coldly wonderfully marginally far
                upon excluding.
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>
    <!-- My Speciality -->
    <!-- My Challenge -->
    <!-- Latest Post -->
    <v-divider class="ma-5" id="latest-post"></v-divider>
    <section>
      <v-container grid-list-xs class="mt-5">
        <h1>Latest Post</h1>
        <LatestPost
          :feedUrl="latestPost.feedUrl"
          :name="latestPost.name"
          :limit="latestPost.limit"
        />
      </v-container>
    </section>
  </v-main>
</template>

<script>
import LatestPost from '@/components/LatestPost';

export default {
  data: () => ({
    latestPost: {
      feedUrl: 'https://uwaylu.github.io/blog/rss.xml',
      limit: 5,
    },
    projects: [
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
      { title: '', caption: '', type: '', href: '' },
    ],
  }),
  components: {
    LatestPost,
  },
};
</script>

<style scoped></style>
