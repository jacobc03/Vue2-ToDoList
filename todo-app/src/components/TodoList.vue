<template>
	<div>
		<!-- JavaSctipt expression in Vue are enclosed in double curly brackets -->
		<!-- The following 2 lines gives a count of how many todos items have a done value of true or false -->
		<p>Completed Tasks:{{todos.filter(todo => {return todo.done === true}).length}}</p>
		<p>Pending Tasks:{{todos.filter(todo => {return todo.done === false}).length}}</p>
		<div class="ui centered card" v-for="todo in todos">
			<div class="content">
				<div class="header">
				<!-- displays the title for each todos item -->
					{{ todo.title }}
				</div>
				<div class="meta">
					{{ todo.project }}
				</div>
				<div class="extra content">
					<span class="right floated edit icon">
						<i class="edit icon"></i>
					</span>
				</div>
			</div>
			<div class="ui bottom attached green basic button" v-show="todo.done">
				Completed
			</div>
			<div class="ui bottom attached red basic button" v-show="!todo.done">
				Complete
			</div>
		</div>
	</div>
</template>

<script type = "text/javascript">

export default {
  props: ['todos'],
  components: {

  }
}
</script>
<style>
	
</style>
