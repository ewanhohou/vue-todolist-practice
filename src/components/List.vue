<template>
  <div class="view">
    <h1 class="title">{{title}}</h1>
    <input type="text" @keyup.enter="addData" v-model="newStr">
    <ul>
      <li v-for="item in items" v-bind:class="{finish:item.isFinished}" 
      @click="toggleFinish(item)">
        {{item.text}}
      </li>
    </ul>
  </div>
</template>

<script>
  export default{
    name: "list",
    data(){
      return {
        title: "TodoList",
        items: [
          // {
          //   text: "sleep",
          //   isFinished:false
          // },
          //   {
          //   text: "eat",
          //   isFinished:true
          // },
        ],
        newStr:'',
      }
    },
    methods: {
      toggleFinish: function(item){
        item.isFinished = !item.isFinished;
      },
      addData: function(){
        this.items.push(
          {
            text:this.newStr,
            isFinished:false
        },
        );

        this.$emit('myMsg',this.newStr);


        this.newStr = '';


      }
    }

  }
</script>

<style>
.view {
  width:400px;
  border: 1px solid gray;
  margin: 20px auto;
}
.view .title {
border-bottom: 1px solid gray;
}
.view ul li {
  margin: 10px 0;
  list-style: none;
}
.view .finish {
  color:gray;
  text-decoration: line-through;
}
</style>
