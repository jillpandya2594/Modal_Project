<template><!-- Every component must have a template .template is a vue tag ,
 it is injected to DOM when the app renders-->

  <h1>{{ title }}</h1>
<p>Welcome</p>
  <input type="text" ref="name"/>
  <button @click="handleClick">Click Me!!!</button>

<div v-if="showModal">
  <Modal  theme="sale" @close="toggleModal">
  <template v-slot:links>
  <a href="#">Sign up</a>
  <a href="#">More info</a>
  </template>
  <h1>Ninja Swag</h1>
  <p>grab your ninja swag right away!</p>
  </Modal>
</div>
<button  @click.alt="toggleModal">Show Modal alt</button><!--- alt is the event modifier-->
  
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>-->
</template>

<script>
import Modal from "./components/Modal.vue"

export default { //The component object is being exported//
  name: 'App',
  components:{Modal},
  data(){
    return{
      title:'My first Vue app :)',
      showModal: false

    }
    
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')// classList.add('active') is just plain javascript nothing Vue about it  //
      this.$refs.name.focus()// focuses the form field in the browser//
    },
    toggleModal(){
      this.showModal=!this.showModal
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
h1{
  border-bottom:5px  solid  #ddda4d;
  display:inline-block;
  padding: 10px;
}
</style>
