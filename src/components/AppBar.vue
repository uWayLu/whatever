<template>
  <v-app-bar app height="80px">
    <v-app-bar-nav-icon class="ml-2">
      <v-avatar>
        <img
          src="https://avatars.githubusercontent.com/u/21689326?s=460&u=3659405c346f21ac9c082fbf72c3d18626e1c4d0&v=4"
          alt="Webb Lu"
        />
      </v-avatar>
    </v-app-bar-nav-icon>
    <span class="ml-3 text-h5 font-weight-bold">WebbLu</span>
    <v-spacer></v-spacer>
    <v-btn text v-for="(link, idx) in links" :key="idx" :to="link.path">
      {{ link.title }}
    </v-btn>
    <v-btn text href="https://uwaylu.github.io/blog">Blog</v-btn>
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    links: [
      { title: 'Home', path: '/' },
      { title: 'Gist & Repo', path: '#project' },
      { title: 'Latest Post', path: '#latest-post' },
    ],
  }),
};
</script>
