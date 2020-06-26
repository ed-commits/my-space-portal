<template>
  <div v-if="apod">
    <h2>{{ apod.title }}</h2>
    <img :src="apod.url" />
    <p>{{ apod.explanation }}</p>
    <i>Copyright: {{ apod.copyright }}</i>

    <p class="credit">Information from: https://api.nasa.gov/</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      apod: undefined
    };
  },
  mounted() {
    const url = "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY";
    fetch(url)
      .then(res => res.json())
      .then(data => (this.apod = data));
  }
};
</script>

<style>
</style>
