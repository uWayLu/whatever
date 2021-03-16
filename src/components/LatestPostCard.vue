<template>
  <v-container>
    <v-card elevation="2" outlined class="px-2">
      <v-card-title class="text-h5 mb-2">
        <a :href="article.link">{{ article.title }}</a>
      </v-card-title>
      <v-card-subtitle class="pb-0 text-left">{{ article.content }}</v-card-subtitle>

      <v-card-actions class="py-1">
        <v-list-item dense>
          <v-list-item-avatar color="grey darken-3">
            <v-img
              class="elevation-2"
              alt="WebbLu"
              src="https://avatars.githubusercontent.com/u/21689326?s=460&u=3659405c346f21ac9c082fbf72c3d18626e1c4d0&v=4"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-subtitle class="text-left">
              {{ this.getHostname() }}
              <span class="mx-1">·</span>
              {{ this.getDateTime() }}
            </v-list-item-subtitle>
          </v-list-item-content>

          <v-spacer></v-spacer>
          <v-btn color="primary" :href="article.link" icon>
            <v-icon>mdi-book-open-page-variant</v-icon>
          </v-btn>
        </v-list-item>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
const parseDate = (tdate) => {
  const systemDate = new Date(Date.parse(tdate));
  const userDate = new Date();
  const diff = Math.floor((userDate - systemDate) / 1000);
  if (diff < 59) {
    return `${diff}s`;
  }
  if (diff <= 3540) {
    return `${Math.round(diff / 60)}m`;
  }
  if (diff <= 86400) {
    return `${Math.round(diff / 3600)}h`;
  }
  if (diff < 604800) {
    return `${Math.round(diff / 86400)}d`;
  }
  return systemDate.toString().substring(4, 10);
};
export default {
  name: 'Article',
  props: ['article'],
  methods: {
    getHostname() {
      let hn;
      try {
        const urlObj = new URL(this.article.link);
        hn = urlObj.hostname.replace('www.', '').replace('ww2.', '');
      } catch (e) {
        // eslint-disable-next-line no-console
        console.error(e.toString());
      }
      return hn;
    },
    getDateTime() {
      let dt;
      if (this.article.isoDate) dt = parseDate(this.article.isoDate);
      return dt;
    },
  },
};
</script>

<style scoped>
</style>
