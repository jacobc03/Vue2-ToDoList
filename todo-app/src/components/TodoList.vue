<template>
	<div>
		<!-- JavaSctipt expression in Vue are enclosed in double curly brackets -->
		<!-- The following 2 lines gives a count of how many todos items have a done value of true or false -->
		<p>Completed Tasks:{{todos.filter(todo => {return todo.done === true}).length}}</p>
		<p>Pending Tasks:{{todos.filter(todo => {return todo.done === false}).length}}</p>
		<!-- passing the data to the todo component to render the todo list -->
		<todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
	</div>
</template>

<script type = "text/javascript">

import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    deleteTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos.splice(todoIndex, 1)
    }
  }
}
</script>
<style scoped>
p.tasks {
  text-align: center;
}
</style>
