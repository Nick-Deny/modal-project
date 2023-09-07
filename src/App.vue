<template>
 <h1>{{ title }}</h1>
 <input type="text" ref="name">
 <button @click="handleClick">click me</button>
 <!-- 3) to use it in the template -->
 <Modal />
</template>

<script>
// 1) Need to import the modal
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  // 2) and register the modal as a component
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)'
    }
  },
  methods: {
    handleClick () {
      // this - refers to component
      // $refs - get access to any ref that we name
      // name - access the ref named "name"
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
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
  width: fit-content;
  margin: 0 auto;
  padding-bottom: 1rem;
  margin-bottom: 1rem;
}
</style>
