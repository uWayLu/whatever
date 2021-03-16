<template>
  <v-main>
    <section>
      <v-parallax
        src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
        height="600"
      >
        <v-container>
          <v-row align="center">
            <v-col>
              <h1
                class="white--text mb-2 display-1 text-xs-center"
                style="font-weight: 900; text-shadow: 3px 2px #000000"
              >
                Attack!
              </h1>
              <div
                class="white--text subheading mb-3 text-xs-center"
                style="font-weight: 900; text-shadow: 2px 2px #000000"
              >
                Coffe Soda Give Me Something
              </div>
              <h5>Coming Soon...</h5>
            </v-col>
            <v-col>
              <v-img
                src="http://res.hpoi.net.cn/gk/cover/n/2015/02/a67d87bd0eba453b864f5daf1dce5fa5.jpg?date=1464613555000"
                max-height="500"
              ></v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
    </section>
    <!-- About -->
    <section id="about">
      <v-container class="mt-5">
        <h1>About</h1>
        <v-row justify="center" class="mt-1">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Pellentesque sit amet ante pretium, porttitor urna nec, vehicula
            odio. Aliquam facilisis semper urna congue efficitur. Ut at
            tristique nisl. Curabitur ac justo id nulla vestibulum bibendum vel
            porttitor nisl. Duis imperdiet cursus magna, sed aliquam odio
            lacinia ut. Aenean ullamcorper et sapien id ultrices. Morbi ornare
            sit amet neque nec vulputate. Sed pharetra ornare convallis.
            Phasellus sapien ligula, efficitur nec congue ac, dignissim a dui.
            Phasellus malesuada nec nisl vel laoreet.
          </p>

          <v-btn color="blue" class="ma-1" text icon
            ><v-icon large>mdi-linkedin</v-icon>
          </v-btn>
          <v-btn color="black" class="ma-1" text icon
            ><v-icon large>mdi-github</v-icon>
          </v-btn>
          <v-btn color="blue lighten-2" class="ma-1" text icon
            ><v-icon large>mdi-twitter</v-icon>
          </v-btn>
        </v-row>
      </v-container>
    </section>
    <v-divider class="ma-5"></v-divider>
    <!-- Project -->
    <section id="project">
      <v-container grid-list-xs class="mt-5">
        <h1>Project</h1>
        <v-row v-for="i in 2" :key="i" class="mt-1">
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
  }),
  components: {
    LatestPost,
  },
};
</script>

<style scoped></style>
