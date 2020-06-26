<template>
  <div>
    <ul v-if="astros">
      <p>There are currently {{ astros.number }} astronauts in space:</p>
      <li v-for="(astro, key) in astros.people" :key="key">{{ astro.name}} on {{ astro.craft }}</li>
    </ul>
    <p class="credit">Information from: http://api.open-notify.org/astros.json</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      astros: undefined
    };
  },
  mounted() {
    fetch("http://api.open-notify.org/astros.json")
      .then(res => res.json())
      .then(data => (this.astros = data));
  }
};
</script>

<style>
</style>
