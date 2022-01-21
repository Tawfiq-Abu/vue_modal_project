<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal v-bind:header="header" :text="text" theme='sale' @close="toggleModal"/>
  </div>
  <button @click.alt="toggleModal">show modal(alt)</button>
  
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
      header:'this is some text inside the props',
      text:'Elements of programming interviews in python',
      showModal:false,
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
</style>
