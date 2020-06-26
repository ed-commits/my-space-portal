<template>
  <div>
    <ul v-if="astros">
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
.credit {
    text-align: right;
    font-style: italic;
    font-size: 0.8em;
    margin: 0;
}
</style>
