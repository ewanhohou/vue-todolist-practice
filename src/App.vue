<template>
  <div id="app">
    <HeaderView :msg="title"></HeaderView>  
    <img src="./assets/logo.png">

    <ListView @myMsg='getData'></ListView>  
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import ListView from './components/List'
import HeaderView from './components/Header'

export default {
  name: 'app',
  components: {
    ListView,HeaderView
  },
  data(){
    return {
      title: "Vue"
    }
  },
  methods: {
    getData(msg){
      console.log(msg)
      this.title = msg;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
