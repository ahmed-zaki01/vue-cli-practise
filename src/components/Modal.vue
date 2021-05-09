<template>
  <div class="modal-container" ref="modal">
    <div class="backdrop">
      <div class="modal">
        <div class="modal-header">
          <h1>Modal Title</h1>
        </div>
        <div class="modal-content">
          <p>Modal Content</p>
        </div>
        <div class="modal-footer">
          <button @click="closeModal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    closeModal() {
      this.$refs.modal.style.display = "none";
      this.$emit("getModalRef", this.$refs.modal);
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: #fff;
  border-radius: 5px;
}

.backdrop {
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
}

.modal-header h1 {
  color: cornflowerblue;
}

.modal-content p {
  font-style: normal;
}
</style>
