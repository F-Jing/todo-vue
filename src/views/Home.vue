<template>
  <div class="todoapp" v-cloak>
    <!-- <TheHeader :handle-add-todo="handleAddTodo" /> -->
    <!-- <TheHeader :todos="todos" /> -->
    <!-- <TheHeader @add-todo="handleAddTodo" /> -->
    <!-- <TheHeader :todos.sync="todos" /> -->
    <!-- <TheHeader :todos="todos" @update:todos="handleUpdateTodos" /> -->
    <!-- <TheList :todos.sync="todos" :filter="filter" /> -->
    <!-- <TheFooter :todos.sync="todos" :filter.sync="filter" /> -->
    <TheHeader />
    <TheList />
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from './../components/TheHeader'
import TheList from './../components/TheList'
import TheFooter from './../components/TheFooter'
export default {
  // data () {
  //   return {
  //     todos: [
  //       {
  //         title: '任务一',
  //         completed: false
  //       },
  //       {
  //         title: '任务二',
  //         completed: true
  //       }
  //     ],
  //     // editTodo: '',
  //     // beforeEditCache: '',
  //     // newTodo: null,
  //     filter: 'all'
  //   }
  // },
  // created () {
  //   this.fetchFilter()
  // },
  // watch: {
  //   $route: 'fetchFilter'
  // },
  // methods: {
  //   fetchFilter: function () {
  //     const filter = this.$route.params.filter
  //     this.filter = filter
  //   }
  // },
  // methods: {
  //   handleEdit (todo) {
  //     this.editTodo = todo
  //     this.beforeEditCache = todo.title
  //   },
  //   handleEditDone (todo) {
  //     if (todo.title.trim()) {
  //       this.editTodo = null
  //       this.beforeEditCache = null
  //     }
  //   },
  //   handleEditCancel (todo) {
  //     todo.title = this.beforeEditCache
  //     this.editTodo = null
  //     this.beforeEditCache = null
  //   },
  //   handleAddTodo () {
  //     this.todos.push({
  //       title: this.newTodo,
  //       completed: false
  //     })
  //     this.newTodo = ''
  //   },
  //   handleAddTodo (todo) {
  //     this.todos.push(todo)
  //   },
  //   handleUpdateTodos (todos) {
  //     this.todos = todos
  //   },
  //   handleRemoveTodo (todo) {
  //     const index = this.todos.indexOf(todo)
  //     this.todos.splice(index, 1)
  //   },
  //   handleRemoveAllCompletedTodo () {
  //     this.todos = this.todos.filter(data => !data.completed)
  //   }
  //   handleChangeFilter (filter) {
  //     this.filter = filter
  //   }
  // },
  components: {
    TheHeader,
    TheList,
    TheFooter
  }
  // directives: {
  //   'todo-focus': function (el, binding) {
  //     if (binding.value) {
  //       el.focus()
  //     }
  //   }
  // },
  // computed: {
  //   allCompleted: {
  //     get: function () {
  //       return this.todos.every(data => data.completed)
  //     },
  //     set: function (value) {
  //       this.todos.forEach(todo => { todo.completed = value })
  //     }
  //   },
  //   hasCompleted () {
  //     return this.todos.some(data => data.completed)
  //   }
  //   showTodos () {
  //     const filter = this.filter
  //     return this.todos.filter(data => {
  //       if (filter === 'all') {
  //         return true
  //       } else if (filter === 'active') {
  //         return !data.completed
  //       } else if (filter === 'completed') {
  //         return data.completed
  //       }
  //     })
  //   }
  // }
}
</script>
<style lang="less">
@import "./../assets/base.css";
@import "./../assets/index.css";
</style>
