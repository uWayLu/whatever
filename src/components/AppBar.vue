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
    <div class="hidden-md-and-up">
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-app-bar-nav-icon slot="activator" v-bind="attrs" v-on="on">
            <v-icon>mdi-menu</v-icon>
          </v-app-bar-nav-icon>
        </template>
        <v-list outlined>
          <v-list-item
            v-for="link in links"
            :key="link.title"
            link
            :to="link.path"
            class="text-body-1"
          >
            <v-list-item-title>
              {{ link.title }}
            </v-list-item-title>
          </v-list-item>
          <v-list-item href="https://uwaylu.github.io/stockTool"
            ><v-list-item-title>韭菜盒</v-list-item-title></v-list-item
          >
          <v-list-item href="https://uwaylu.github.io/blog"
            ><v-list-item-title>Blog</v-list-item-title></v-list-item
          >
        </v-list>
      </v-menu>
    </div>
    <div class="hidden-sm-and-down">
      <v-btn text v-for="link in links" :key="link.title" :to="link.path">
        {{ link.title }}
      </v-btn>
      <v-btn text href="https://uwaylu.github.io/stockTool">韭菜盒</v-btn>
      <v-btn text href="https://uwaylu.github.io/blog">Blog</v-btn>
    </div>
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
