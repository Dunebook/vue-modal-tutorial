<template>
  <div id="app">
    <h1>Vue Modal Tutorial</h1>
    <button @click="openModal" v-if="!showModal">Open Modal</button>
    <app-modal v-if="showModal" :showModal=showModal @clicked="onClickChild">
      <div slot="header">
        <h3 class="modal-title">
          Join Dunebook.com today
        </h3>
      </div>
      <div slot="body">
        <p>
          Get the best in Python, Angular, React, Vue, NodeJS & more directly to your inbox.
        </p>
      </div>
    </app-modal>
  </div>
</template>
<script>
import AppModal from './components/AppModal';
export default {
  components: {
    AppModal
  },
  data() {
    return {
      showModal: false
    }
  },
  methods: {
    openModal() {
      this.showModal = true;
    },
    onClickChild () {
      this.showModal = false;
    }
  },
}
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>