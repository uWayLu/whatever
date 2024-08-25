<template>
  <v-footer dark padless>
    <v-card flat tile class="indigo lighten-1 white--text flex text-center">
      <v-card-text>
        <v-btn
          v-for="place in findMePlaces"
          :key="place.icon"
          class="white--text mx-1"
          icon
          :href="place.href"
          :target="place.target"
        >
          <v-icon size="24px">
            {{ place.icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        &copy; 2021-{{ new Date().getFullYear() }} <strong>uWayLu | Personal Web Page</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'],
    findMePlaces: [
      // { icon: 'mdi-facebook', href: '' },
      // { icon: 'mdi-twitter', href: '' },
      {
        icon: 'mdi-linkedin',
        href: 'https://www.linkedin.com/in/webb-lu/',
        target: '_blank'
      },
      {
        icon: 'mdi-github',
        href: 'https://www.github.com/uwaylu/',
        target: '_blank'
      }
    ]
  })
}
</script>
