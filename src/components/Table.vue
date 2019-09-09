<template>
  <div>
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
        <tr v-for="(item,index) in tableItem" @click="modalShow(item)">
          <td>{{item.id}}</td>
          <td>{{item.firstName}}</td>
          <td>{{item.lastName}}</td>
          <td>{{item.email}}</td>
          <td>{{item.phone}}</td>
        </tr>
      </tbody>
    </table>
    <div class="modal" :class="isVisible  ? 'show': '' ">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Modal title</h5>
            <button
              @click="isVisible = false"
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body" v-bind="row">
            <div>
              <span>id:</span>
              {{row.id}}
            </div>
            <div>
              <span>firstName:</span>
              {{row.firstName}}
            </div>
            <div>
              <span>lastName:</span>
              {{row.lastName}}
            </div>
            <div>
              <span>email:</span>
              {{row.email}}
            </div>
            <div>
              <span>phone:</span>
              {{row.phone}}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableItem: [],
      isVisible: false,
      row: ""
    };
  },
  created: async function() {
    const response = await fetch(
      "http://www.filltext.com/?rows=32&id=%7Bnumber%7C1000%7D&firstName=%7BfirstName%7D&lastName=%7BlastName%7D&email=%7Bemail%7D&phone=%7Bphone%7C(xxx)xxx-xx-xx%7D&address=%7BaddressObject%7D&description=%7Blorem%7C32%7D"
    );
    const data = await response.json();
    this.tableItem = data;
  },
  methods: {
    modalShow(row) {
      this.isVisible = true;
      this.row = row;
    }
  }
};
</script>


<style lang="scss" scoped>
.show {
  display: block !important;

}
tr {
  cursor: pointer;
  &:hover {
    background-color: darken(#fff, 10%);
    transition: 0.3s;
  }
 
}
.modal {
  &-dialog {
    width: 700px;
  }
  &-body {
    display: flex;
    flex-direction: column;
  }
}
</style> >



