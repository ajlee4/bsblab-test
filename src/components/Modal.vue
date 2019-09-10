<template>
  <div class="modal" :class="isVisible ? 'show' : '' ">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Modal title</h5>
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label="Close"
            @click="close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
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
</template>

<script>
export default {
  props: {
    isVisible: Boolean,
    row: Object
  },
  data() {
    return {};
  },
  methods: {
    close() {
      this.$emit("closeModal");
    }
  }
};
</script>

<style lang="scss" scoped>
.show {
  display: block !important;
}
.modal {
  &-body {
    display: flex;
    flex-direction: column;
  }
}
</style>