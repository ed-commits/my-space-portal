<template>
  <div v-if="hubble">
    <h2>{{ hubble.name }}</h2>
    <p>{{ hubble.abstract }}</p>
    <img :src="hubble.keystone_image_1x" />
    <p class="credit">Information from: http://hubblesite.org/api/documentation</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hubble: undefined
    };
  },
  mounted() {
    // https://stackoverflow.com/questions/43871637/no-access-control-allow-origin-header-is-present-on-the-requested-resource-whe
    const proxyurl = "https://cors-anywhere.herokuapp.com/";
    const url = "http://hubblesite.org/api/v3/news_release/last/"; // site that doesn’t send Access-Control-*
    fetch(proxyurl + url)
      .then(res => res.json())
      .then(data => (this.hubble = data));
  }
};
</script>

<style>
</style>
