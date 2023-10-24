<template>
  <div class="modal" @click="closeModal">
    <div class="modal-content">
      <span class="close" @click="closeModal">x</span>
      <img class="modal-img" :src="image.fullSize" alt="Full Size Image" />
    </div>
  </div>
</template>

<script>
export default {
  props: ['image'],
  methods: {
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-content {
  background-color: #fff;
  padding: 20px;
  text-align: center;
}

.close {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  font-size: 30px;
  color: #fff;
}

.modal img {
  max-width: 100%;
  max-height: 80vh;
}
</style>
