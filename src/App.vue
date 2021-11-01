<template>
  <!-- <div v-if="showModal">
    <Modal :modaltxt="txt" :textcolor="txtcolor" @close="toggleModal">
      <select name="" id="">
        <option value="">Mercedes</option>
        <option value="">BMW</option>
      </select>
      <template v-slot:links>
        <a href="https://nijat.net">my website</a>
      </template>
    </Modal>
  </div> -->
  <!--<button @click="toggleModal">Toggle Modal</button>-->
  <Game />
</template>

<script>
import Modal from "./components/Modal.vue";
import Game from "./components/Game.vue";
export default {
  name: "App",
  components: {
    Modal,
    Game,
  },
  data() {
    return {
      txt: "Salam qaqa netersen",
      txtcolor: true,
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
