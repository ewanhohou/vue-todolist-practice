<template>
  <div class="headerview">
    <h1>{{msg}}</h1>
  </div>
</template>
<script>
  export default{
    data(){
      return {
        title: "Header...."
      }
    },
    props: {
      msg:{
        type: String,
        default: "default"
      }
    }
  }
</script>
<style>

</style>
