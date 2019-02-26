<template>
  <div class="todos">
    <h1>Simple ToDo App</h1>
    <input @keyup.enter="add" type="text" v-model="title" placeholder="Task to do ...">
    <button @click="add">Add task</button>

    <ul>
        <li v-for="todo in todos">{{todo}}</li>
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
          todos: [
              'Go to ...'
          ]
      }
  },
  
  methods: {
      add(){
          this.todos.push(this.title);
          this.title = "";
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
