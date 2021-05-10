<template>
  <div class="modal-container" ref="modal">
    <div class="backdrop" @click.self="closeModal">
      <div class="modal" :class="{ sale: theme === 'sale' }">
        <div class="modal-header" style="text-align: left">
          <h1>{{ title }}</h1>
        </div>
        <div class="modal-content">
          <p>
            <slot>This is the default content!</slot>
            <slot name="content"></slot>
          </p>
        </div>
        <div class="modal-footer" style="text-align: right">
          <button @click="closeModal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backdrop {
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
}

.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: #fff;
  border-radius: 5px;
}

.modal-header,
.modal-content,
.modal-footer {
  padding: 15px;
}

.modal-header h1 {
  color: cornflowerblue;
}

.modal-content p {
  font-style: normal;
}

.modal.sale {
  background: crimson;
}

.modal.sale h1 {
  color: blanchedalmond;
}

.modal-footer button {
  background: rgb(106, 107, 47);
  color: azure;
  border: 0;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
}

.modal-footer button:hover {
  background: rgba(106, 107, 47, 0.8);
}
</style>
