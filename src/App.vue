<template>
  <div id="app">
    <div class="dashboard">
      <Card title="Who is in space right now?">
        <div slot="body">
          <CurrentlyInSpace/>
        </div>
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
import CurrentlyInSpace from "./components/CurrentlyInSpace.vue";

export default {
  name: "App",
  components: {
    Card,
    CurrentlyInSpace
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

