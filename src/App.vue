<template>
  <header>
    <h2>My Modal</h2>
  </header>

  <div v-if="modalShow">
    <Modal :title="title" :content="content" @close="toggleModal" theme="sale">
      <template #links>
        <h2>This is my first modal</h2>
        <p>This is my first modal content</p>
        <!-- link -->
        <button>
          <a href="www.google.com" target="_blank">Browse Google</a>
        </button>
        <button @click="toggleModal">Close</button>
      </template>
    </Modal>
  </div>
  <div v-if="modalShow2">
    <Modal :title="title" :content="content" @close="toggleModal2">
      <h2>This is my second modal</h2>
      <p>This is my second modal content</p>
      <button>Buy Now</button>
      <button @click="toggleModal2">Close</button>
    </Modal>
  </div>

  <div v-if="modalShow3">
    <Modal
      :title="title"
      :content="content"
      @close="toggleModal3"
      theme="myImg"
    >
      <template #links>
        <div>
          <img
            src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png"
            alt=""
          />
        </div>
        <h2>This is my third modal</h2>
        <p>This is my third modal content</p>
      </template>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal 2</button>
  <button @click="toggleModal3">Open Modal 3</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  data() {
    return {
      modalShow: false,
      modalShow2: false,
      modalShow3: false,
      title: "This is my second modal",
      content: "This is my second modal content",
    };
  },
  components: {
    Modal,
  },
  methods: {
    toggleModal() {
      this.modalShow = !this.modalShow;
    },
    toggleModal2() {
      this.modalShow2 = !this.modalShow2;
    },
    toggleModal3() {
      this.modalShow3 = !this.modalShow3;
    },
  },
  computed: {
    close() {
      this.modalShow = false;
    },
  },
};
</script>

<style>
header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
}

header h2 {
  text-align: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
button {
  margin-top: 20px;
}
a {
  color: black;
  text-decoration: none;
}
</style>
