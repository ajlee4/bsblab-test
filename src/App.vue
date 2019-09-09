<template>
  <div id="app">
    <Table></Table>
  </div>
</template>

<script>
import Table from "./components/Table.vue";
import "bootstrap/dist/css/bootstrap.min.css";

export default {
  name: "app",
  components: {
    Table
  },
  data() {
    return {};
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
