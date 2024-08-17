<template>
  <div class="backdrop" @click.self="modalClose">
    <div
      class="modal"
      :class="{ sale: theme === 'sale', img: theme === 'myImg' }"
    >
      <!-- <h2>{{ title }}</h2>
      <p>{{ content }}</p> -->

      <slot></slot>
      <slot name="links"></slot>
      <slot name="img"></slot>
    </div>
  </div>
</template>

<script>
export default {
  //   props: ["title", "content"],
  props: {
    title: {
      type: String,
      default: () => ({}),
    },
    content: {
      type: String,
      default: () => ({}),
    },
    theme: {
      type: String,
      default: () => ({}),
    },
  },
  methods: {
    modalClose() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 10;
}
.modal {
  width: 400px;
  margin: 100px auto;
  padding: 20px;
  background: #fff;
  border-radius: 10px;
}
.sale {
  background: rgb(209, 104, 122);
  color: #fff;
}
.img {
  background: rgb(31, 204, 109);
  color: #fff;
}
</style>
