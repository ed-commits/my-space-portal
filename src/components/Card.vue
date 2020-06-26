<template>
  <div class="card">
    <div class="card-title">
      <h1>{{ title }}</h1>
    </div>
    <div
      class="card-body"
    ><slot name="body"/></div>
  </div>
</template>

<script>
export default {
  props: ['title']
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
</style>
