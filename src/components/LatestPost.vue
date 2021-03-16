<template>
  <v-container v-if="error"> {{ error }}</v-container>
  <v-container v-else>
    <LatestPostCard
      v-for="(article, index) of getArticles()"
      :key="index"
      :article="article"
    />
  </v-container>
</template>

<script>
import LatestPostCard from '@/components/LatestPostCard';
import RSSParser from 'rss-parser';

export default {
  name: 'Feed',
  components: {
    LatestPostCard,
  },
  props: {
    feedUrl: String,
    name: String,
    limit: Number,
    loadMore: Boolean,
  },
  data() {
    return {
      loading: true,
      error: '',
      feed: {},
    };
  },
  created() {
    this.fetchData();
  },
  watch: {
    feedUrl() {
      this.fetchData();
    },
    limit(newVal, oldVal) {
      if (newVal !== oldVal) {
        this.getArticles();
      }
    },
  },
  methods: {
    async fetchData() {
      this.error = '';
      this.loading = true;
      this.feed = {};
      try {
        const data = await fetch(this.feedUrl);
        if (data.ok) {
          const text = await data.text();
          const parser = new RSSParser();
          parser.parseString(text, (err, parsed) => {
            this.loading = false;
            if (err) {
              this.error = `Error occured while parsing RSS Feed ${err.toString()}`;
            } else {
              this.feed = parsed;
            }
          });
        } else {
          this.error = 'Error occured while fetching the feed';
          this.loading = false;
        }
      } catch (e) {
        if (e.toString() === 'TypeError: Failed to fetch') {
          this.error = 'Error due to CORS policy';
        } else {
          this.error = e.toString();
        }
        this.loading = false;
      }
    },
    getArticles() {
      if (this.feed.items && this.feed.items) {
        return this.feed.items
          .sort((a, b) => (a.isoDate < b.isoDate ? 1 : -1))
          .slice(0, this.limit);
      }
      return undefined;
    },
  },
};
</script>

<style scoped>
</style>
