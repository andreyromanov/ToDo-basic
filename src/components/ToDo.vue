<template>
  <div class="todos">
    <h1>Simple ToDo App</h1>
    <input @keyup.enter="add" type="text" v-model="title" placeholder="Task to do ...">
    <button @click="add">Add task</button>

    <ul>  
        <li v-for="(todo,index) in todos">{{todo}} <span @click="del(index)" class="delete">&nbsp;X&nbsp;</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "todo",
  props: {
    msg: String
  },

  data(){
      return{
          title: '',
          todos: []
      }
  },
  
  methods: {
      add(){
        if(this.title != ''){
          this.todos.unshift(this.title);
          this.title = "";
        }
      },
      del(id){
        this.$delete(this.todos, id);
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.delete{
  padding: 5px;
  border-radius: 50%;
  background-color: red;
}
.delete:hover{
  cursor: pointer;
}
ul{
  list-style-type: none;
}
li{
  margin-top: 15px;
}
</style>
