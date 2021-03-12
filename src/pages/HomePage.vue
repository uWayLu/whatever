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
        <v-row justify="center">
          <h1>About Me</h1>
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
  </v-main>
</template>

<script>
export default {};
</script>

<style scoped></style>
