<template>
  <div class="modal" ref="modal">
    <div class="backdrop">
      <div class="modal-content">
        <p>Modal Content</p>
        <button @click="closeModal">Close</button>
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

<style>
body {
  margin: 0;
  padding: 0;
}

.modal-content {
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
</style>
