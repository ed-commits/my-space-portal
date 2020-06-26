<template>
  <div>
    <div v-if="exoplanets">
      Exoplanets discovered in 2020:
      <div v-for="(exo, key) in exoplanets" :key="key">
        <a :href="exo.pl_pelink"><h3>{{ exo.pl_hostname }}:</h3></a>
        <ul>
          <li>
            <b>Mass:</b>
            {{ exo.pl_bmassj }} M
            <sub>J</sub>.
          </li>
          <li>
            <b>Distance from earth:</b>
            {{ exo.st_dist }} parsecs.
          </li>
          <li>
            <b>Discovery Method:</b>
            {{ exo.pl_discmethod }} using the {{ exo.pl_telescope }}/{{ exo.pl_instrument }}.
          </li>
          <li>
            <b>Number of moons:</b>
            {{ exo.pl_mnum }}.
          </li>
        </ul>
      </div>
    </div>
    <p
      class="credit"
    >Information from: https://exoplanetarchive.ipac.caltech.edu/docs/program_interfaces.html</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      exoplanets: undefined
    };
  },
  mounted() {
    fetch(
      "https://exoplanetarchive.ipac.caltech.edu/cgi-bin/nstedAPI/nph-nstedAPI" +
        "?table=exoplanets" +
        "&select=pl_hostname,pl_discmethod,pl_bmassj,st_dist,pl_disc,pl_telescope,pl_instrument,pl_mnum,pl_pelink" +
        "&where=" +
        encodeURI("pl_disc = 2020") +
        "&order=dec" +
        "&format=json"
    )
      .then(res => res.json())
      .then(data => (this.exoplanets = data.slice(0,10)));
  }
};
</script>

<style>
h3 {
  margin-bottom: 0px;
}

ul {
  margin-top: 0px;
}

a {
  color: black;
}
</style>
