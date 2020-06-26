<template>
  <div>
    <div v-if="launches">
      <div v-for="(launch, key) in launches.result" :key="key">
        <h3>{{ launch.name }} is scheduled to launch on {{ launch.date_str }}</h3>
        <p>{{ launch.launch_description }}</p>
        <ul>
          <li>Launchpad: <b>{{ launch.pad.name }}</b> located at {{ launch.pad.location.name }}, {{ launch.pad.location.country }}</li>
          <li>Vehicle: <b>{{ launch.vehicle.name }}</b> provided by {{ launch.provider.name }}</li>
          </ul>
      </div>
    </div>
    <p class="credit">Information from: https://fdo.rocketlaunch.live/json/launches/next/5</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      launches: undefined
    };
  },
  mounted() {
    fetch("https://fdo.rocketlaunch.live/json/launches/next/5")
      .then(res => res.json())
      .then(data => (this.launches = data));
  }
};
</script>

<style>
</style>
