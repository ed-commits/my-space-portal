<template>
  <div class="card">
    <div class="card-title">
      <h1>
        <span v-on:click="toggle">{{ toggleStatus }}</span>
        {{ title }}
      </h1>
    </div>
    <div class="card-body" v-if="enabled">
      <slot name="body" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["title"],
  data() {
    return {
      enabled: false
    };
  },
  mounted() {
    this.enabled = window.localStorage.getItem(this.title) == 'true';
  },
  computed: {
    toggleStatus() {
      return this.enabled ? "⯆" : "⯈";
    }
  },
  methods: {
    toggle() {
      this.enabled = !this.enabled;
      window.localStorage.setItem(this.title, this.enabled);
    }
  }
};
</script>

<style>
.card {
  border: 1px solid rgb(5, 12, 114);

  margin: 10px;
}

.card-title {
  background-color: rgb(58, 58, 58);
  padding: 0;
}
.card-title h1 {
  margin: 0;
  padding: 10px;
}

.card-body {
  background-color: grey;
  padding: 20px;
}

.credit {
  text-align: right;
  font-style: italic;
  font-size: 0.8em;
  margin: 0;
}

img {
  max-width: 100%;
  max-height: 100%;
  display: block;
}
</style>
