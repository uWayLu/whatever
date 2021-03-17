<template>
  <v-main>
    <section>
      <v-parallax
        src="https://images.pexels.com/photos/1089438/pexels-photo-1089438.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
        height="500"
      >
        <v-row>
          <v-col class="align-self-center" cols="6">
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
          <v-col class="d-flex align-end justify-center" cols="6">
            <v-img
              class="justify-self-end"
              src="./../static/you-thumb-up.png"
              max-width="520"
              gradient
            ></v-img>
          </v-col>
        </v-row>
      </v-parallax>
    </section>
    <!-- About -->
    <section id="about">
      <v-container class="mt-5">
        <h1>About</h1>
        <v-row class="mt-1">
          <v-col
            class="d-flex flex-column justify-space-around justify-space-around"
            cols="12"
            md="6"
          >
            <div class="text-justify">
              索引走過的痕跡；從猴子到普通人？<br />
              人與動物區別，在於思想、工具的使用、有價值觀所權衡。<br />
              透過工具組合各種元素成為 WebbLu 索引頁！
            </div>
            <div class="text-justify">
              本頁索引四散各處的筆記，網誌以及 Github 專案，
              若有任何寶貴的意見，您可以發送到
              <v-btn
                color="secondary"
                x-small
                href="mailto:u.master.o.twn+landing@gmail.com?subject=Recommendation"
                >電子郵箱</v-btn
              >
            </div>
            <div class="align-center">
              <v-btn
                href="https://uwaylu.github.io/Resume/"
                class="blue--text text-body-1 font-weight-bold"
                plain
                x-large
                >- Resume -</v-btn
              >
            </div>
          </v-col>
          <v-col class="align-self-center">
            <span class="text-h6">Coming Soon...</span>
            <v-form ref="form" hidden>
              <v-text-field name="nickname" label="Nickname"></v-text-field>
              <v-text-field name="email" label="E-Mail"></v-text-field>
              <v-text-field name="message" label="Message"></v-text-field>
              <v-btn class="mr-4" color="primary" type="submit" disabled
                >submit</v-btn
              >
            </v-form>
          </v-col>
        </v-row>
        <div class="d-flex">
          <v-divider width="3px" class="ma-5"></v-divider>
          <v-btn
            color="blue"
            class="ma-1"
            text
            icon
            href="https://www.linkedin.com/in/webb-lu/"
            target="_blank"
            ><v-icon large>mdi-linkedin</v-icon>
          </v-btn>
          <v-btn
            color="black"
            class="ma-1"
            text
            icon
            href="https://www.github.com/uwaylu/"
            target="_blank"
            ><v-icon large>mdi-github</v-icon>
          </v-btn>
          <v-divider class="ma-5"></v-divider>
        </div>
      </v-container>
    </section>
    <!-- Project -->
    <section id="project">
      <v-container class="mt-2">
        <h1>Gist & Repo</h1>
        <v-container
          fluid
          class="d-flex justify-space-between text-justify flex-wrap"
        >
          <v-card
            rounded="lg"
            v-for="(project, index) in projects"
            :key="index"
            class="ma-1 flex-grow-1 d-flex flex-column justify-space-around"
          >
            <v-card-title class="text-subtitle-1">{{
              project.title
            }}</v-card-title>

            <v-card-subtitle class="text-right">
              <v-chip
                v-for="tag in project.tags"
                :key="tag + index"
                small
                outlined
                color="blue"
                class="mx-1 mb-1"
                >{{ tag }}</v-chip
              >
            </v-card-subtitle>

            <v-card-text v-if="project.captions" class="text-subtitle-2">
              <div v-for="caption in project.captions" :key="caption">
                {{ caption }}
              </div>
            </v-card-text>

            <v-card-text v-if="project.hrefs" class="py-1 ml-3 text-right">
              <v-btn
                plain
                icon
                color="black"
                v-for="href in project.hrefs"
                :key="href.title"
                target="_blank"
                :href="href.href"
              >
                <v-icon>mdi-{{ href.icon }}</v-icon>
              </v-btn>
            </v-card-text>
          </v-card>
        </v-container>
      </v-container>
    </section>
    <!-- My Speciality -->
    <!-- My Challenge -->
    <!-- Latest Post -->
    <v-divider class="ma-5"></v-divider>
    <section id="latest-post">
      <v-container class="mt-5">
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
      {
        title: 'PHP 小助手包',
        captions: ['composer install webblu/phpmyhelper'],
        hrefs: [
          {
            title: 'Packagist: webblu/phpmyhelper',
            href: 'https://packagist.org/packages/webblu/phpmyhelper',
            icon: 'package-down',
          },
          {
            title: 'Github',
            href: 'https://github.com/uWayLu/phpmyhelper',
            icon: 'github',
          },
        ],
        tags: ['PHP', 'Composer', 'Packagist'],
      },
      {
        title: 'PHP 解析 CNAME 成 hostname',
        captions: ['Gist', '或許會加到 php-myhelper （如果繼續維護的話）'],
        hrefs: [
          {
            title: 'Github',
            href:
              'https://gist.github.com/uWayLu/243d4681f1e43b18e73ccfa30ceffda0',
            icon: 'github',
          },
        ],
        tags: ['PHP'],
      },
      // { title: 'PTT 定時自動登入', captions: [''], hrefs: '', tags: [] },
      {
        title: '打包 sikulix2 的 docker image',
        captions: [
          'docker pull uwaylu/ubuntu-sikulix2-base',
          '在 docker 中執行 sikulix 做圖像比對',
        ],
        hrefs: [
          {
            title: 'DockerHub',
            href: 'https://hub.docker.com/r/uwaylu/ubuntu-sikulix2-base',
            icon: 'docker',
          },
          {
            title: 'Github',
            href: 'https://github.com/uWayLu/ubuntu-sikulix2-base',
            icon: 'github',
          },
        ],
        tags: ['Docker', 'SikuliX'],
      },
      {
        title: '打包 sikulix2 + selenium 的 docker image',
        captions: [
          'run sikulix in selenium offcial chrome docker (for selelium-hub) ',
        ],
        hrefs: [
          {
            title: 'DockerHub',
            href: 'https://hub.docker.com/r/uwaylu/node-chrome-debug-sikulix',
            icon: 'docker',
          },
          {
            title: 'Github',
            href:
              'https://github.com/uWayLu/selenium-node-chrome-debug-sikulix',
            icon: 'github',
          },
        ],
        tags: ['Docker', 'SikuliX', 'Selenium'],
      },
      {
        title: 'Contribute: MOPCON 2018',
        captions: ['PHP Official Website Contributor', 'Site Staff'],
        hrefs: [
          {
            title: 'MOPCON 2018',
            href: 'https://mopcon.org/2018/',
            icon: 'web',
          },
          {
            title: 'Github',
            href: 'https://github.com/uWayLu/MOPCON',
            icon: 'github',
          },
        ],
        tags: ['PHP', 'MOPCON', 'Contribution'],
      },
      {
        title: 'Contribute: Vuepress-the-blog',
        captions: ['A little contribution', ' fix: web feed link 404 when set custom base'],
        hrefs: [
          {
            title: '@vuepress/plugin-blog',
            href: 'https://vuepress.vuejs.org/plugin/official/plugin-blog.html',
            icon: 'vuejs',
          },
          {
            title: 'Github',
            href: 'https://github.com/vuepress/vuepress-theme-blog',
            icon: 'github',
          },
        ],
        tags: ['Contribution', 'Vue', 'Vuepress'],
      },
    ],
    notes: [
      { title: 'Evernote', caption: '', type: '', hrefs: '' },
      { title: 'Notion', caption: '', type: '', hrefs: '' },
      { title: 'HackMD', caption: '', type: '', hrefs: '' },
    ],
  }),
  components: {
    LatestPost,
  },
};
</script>

<style scoped></style>
