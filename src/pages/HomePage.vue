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
    <!-- About Me -->
    <section>
      <v-container class="mt-5">
        <h1>About Me</h1>
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
    <!-- Project -->
    <section>
      <v-container grid-list-xs class="mt-5">
        <h1>Project</h1>
        <v-row v-for="i in 2" :key="i" class="mt-1">
          <v-col v-for="j in 4" :key="j">
            <v-card shaped>
              <v-card-title primary-title>
                Card {{ 4 * (i - 1) + j }}
              </v-card-title>
              <v-card-subtitle>
                subtitle
              </v-card-subtitle>
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
    <section>
      <v-container grid-list-md class="mt-5">
        <h1>Latest Post</h1>
        <v-row class="mt-1">
          <v-col v-for="j in 3" :key="j">
            <v-card class="mx-auto" max-width="344">
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                height="200px"
              ></v-img>

              <v-card-title>
                Top western road trips
              </v-card-title>

              <v-card-subtitle>
                1,000 miles of wonder
              </v-card-subtitle>

              <v-card-actions>
                <v-btn color="orange lighten-2" text>
                  Explore
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon @click="show = !show">
                  <v-icon>{{
                    show ? 'mdi-chevron-up' : 'mdi-chevron-down'
                  }}</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div v-show="show">
                  <v-divider></v-divider>

                  <v-card-text>
                    I'm a thing. But, like most politicians, he promised more
                    than he could deliver. You won't have time for sleeping,
                    soldier, not with all the bed making you'll be doing. Then
                    we'll go with that data file! Hey, you add a one and two
                    zeros to that or we walk! You're going to do his laundry?
                    I've got to find a way to escape.
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>
  </v-main>
</template>

<script>
export default {};
</script>

<style scoped></style>
