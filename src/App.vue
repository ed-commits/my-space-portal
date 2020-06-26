<template>
  <div id="app">
    <div class="dashboard">
      <Card title="Who is in space right now?">
        <div slot="body">
          <CurrentlyInSpace/>
        </div>
      </Card>
      <Card title="Upcoming Launches">
        <div slot="body">
          <UpcomingLaunches/>
        </div>
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
import UpcomingLaunches from "./components/UpcomingLaunches.vue";

export default {
  name: "App",
  components: {
    Card,
    CurrentlyInSpace,
    UpcomingLaunches
  }
};
</script>

<style>
#app {
  max-width: 80ch;
  margin: 0 auto;
  font-family: 'Assistant';
  font-size: 1.2rem;
}

.dashboard {
}

</style>

