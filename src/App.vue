<template>
  <div id="app">
    <Table :table="table" @modalShow="modalShow"></Table>
    <Modal :row="modalInfo" :isVisible="modalVisible" @closeModal="closeModal"></Modal>
  </div>
</template>

<script>
import Table from "./components/Table.vue";
import Modal from "./components/Modal.vue";
import "bootstrap/dist/css/bootstrap.min.css";

export default {
  name: "app",
  components: {
    Table,
    Modal
  },
  data() {
    return {
      table: [],
      modalInfo: {},
      modalVisible: false
    };
  },
  created: async function() {
    const response = await fetch(
      "http://www.filltext.com/?rows=32&id=%7Bnumber%7C1000%7D&firstName=%7BfirstName%7D&lastName=%7BlastName%7D&email=%7Bemail%7D&phone=%7Bphone%7C(xxx)xxx-xx-xx%7D&address=%7BaddressObject%7D&description=%7Blorem%7C32%7D"
    );
    const data = await response.json();
    this.table = data;
  },
  methods: {
    modalShow(row) {
      this.modalInfo = row;
      this.modalVisible = true;
    },
    closeModal() {
      this.modalVisible = false;
    }
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
