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
    this.enabled = window.localStorage.getItem(this.title) == "true";
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
  margin: 20px;
}

.card-title {
  background-color: rgb(189, 199, 230);
  padding: 0;
  border-radius: 30px 30px 0px 0px;
}

.card-title h1 {
  margin: 0;
  padding: 10px;
}

span {
  font-size: 0.8em;
}

.card-body {
  background-color: #cfe3e8;
  padding: 20px;
  border-radius: 0px 0px 30px 30px;
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
