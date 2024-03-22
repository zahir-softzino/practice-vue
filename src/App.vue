<template>
  <h2>{{ title }}</h2> 
  <br>
  <div v-if="showModal">
    <ModalShow :header="header" :text="text" theme="sale" @close="toggleModal"/>
  </div>
  <button @click.alt="toggleModal">open modal(alt)</button>
</template>

<script>
import ModalShow from './components/ModalShow.vue';

export default {
  name: 'App',
  components: { ModalShow },
  data(){
    return {
      title: 'This is title',
      header: 'This is header.',
      text: 'This is a dummy text',
      showModal: false
    }
  },
  methods:{
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

h2{
  border-bottom: 2px solid #444;
  padding-bottom: 10px;
  display: inline-block;
}
</style>
