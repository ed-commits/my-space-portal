<template>
  <div id="app">
    <div class="dashboard">
      <Card title="Card1">
        <div slot="body">body1</div>
      </Card>
      <Card title="Card2">
        <div slot="body">body2</div>
      </Card>
      <Card title="Card3">
        <div slot="body">body3</div>
      </Card>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    Card
  }
};
</script>

<style>
#app {
  width: 80ch;
  margin: 0 auto;
  font-family: 'Assistant';
}

.dashboard {
}
</style>

