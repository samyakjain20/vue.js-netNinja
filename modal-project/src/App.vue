<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal theme="sale"  @close="toggleModal">
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag at half price!</p>

      <template v-slot:links>
        <a href="">signup now</a>
        <a href="">more info</a>
      </template>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Signup to newsletter</h1>
      <p>For updates and promocodes!</p>
    </Modal>
  </div>

  <br>
  <p>Welcome...</p>
  <button @click.alt="toggleModal"> Open Modal(alt)</button>
  <button @click="toggleModalTwo"> Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return{
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }
}
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
