<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal v-bind:header="header" :text="text" theme='sale' @close="toggleModal">
      <template v-slot:links>
        <a href="#" class="lil">About us</a>
        <a href="#">Contact us</a>
      </template>
      <h1>okay now this is using a slot instead of a prop</h1>
      <p>interesting items being learnt over here man</p>
    </Modal>
  </div>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to our channel </h1>
      <p>For interesting contents and giveaways</p>
    </Modal>
  </teleport>

  <button @click.alt="toggleModal">show modal(alt)</button>
  <button @click="toggleModalTwo">show modal</button>
  
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click me</button> -->
</template>

<script>
import Modal from './components/Modal.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: { Modal},
  data () {
    return {
      title:'My first Vue App:)',
      showModal:false,
      showModalTwo:false,
    }
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
