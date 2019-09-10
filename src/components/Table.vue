<template>
  <table class="table">
    <thead>
      <tr>
        <th>Id</th>
        <th>FirstName</th>
        <th>LastName</th>
        <th>Email</th>
        <th>Phone</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item,index) in table" @click="viewDetails(item)" :key="index">
        <td>{{item.id}}</td>
        <td>{{item.firstName}}</td>
        <td>{{item.lastName}}</td>
        <td>{{item.email}}</td>
        <td>{{item.phone}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    table: [Array, Object]
  },
  data() {
    return {};
  },

  methods: {
    viewDetails(row) {
      this.$emit("modalShow", row);
    }
  }
};
</script>


<style lang="scss" scoped>
tr {
  cursor: pointer;
  &:hover {
    background-color: darken(#fff, 10%);
    transition: 0.3s;
  }
}
</style> >



