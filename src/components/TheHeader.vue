<template>
  <header class="header">
    <h1>todos</h1>
    <input class="new-todo" autofocus autocomplete="off" placeholder="What needs to be done?" v-model="newTodo" @keyup.enter="addTodo" />
  </header>
</template>
<script>
export default {
  name: 'TheHeader',
  // 方法1父组件把自身属性的方法传递给子组件
  // props: {
  //   handleAddTodo: {
  //     type: Function
  //   }
  // },
  // 方法2把数据传递到子组件
  // props: {
  //   todos: {
  //     type: Array,
  //     default: () => []
  //   }
  // },
  data () {
    return {
      newTodo: ''
    }
  },
  methods: {
    // 方法1
    // addTodo: function () {
    //   this.handleAddTodo({
    //     title: this.newTodo,
    //     completed: false
    //   })
    //   this.newTodo = ''
    // }
    // 方法2
    // addTodo: function () {
    //   this.todos.push({
    //     title: this.newTodo,
    //     completed: false
    //   })
    //   this.newTodo = ''
    // }
    // 方法3子组件内建emit，父组件监听
    // addTodo: function () {
    //   this.$emit('add-todo', {
    //     title: this.newTodo,
    //     completed: false
    //   })
    //   this.newTodo = ''
    // }
    // 方法4updata:属性名的模式触发事件，使用sync缩写修饰符
    // addTodo: function () {
    //   const todos = [...this.todos]
    //   todos.push({
    //     title: this.newTodo,
    //     completed: false
    //   })
    //   this.$emit('update:todos', todos)
    //   this.newTodo = ''
    // }
    addTodo: function () {
      this.$store.commit('addTodo', {
        title: this.newTodo,
        completed: false
      })
      this.newTodo = ''
    }
  }
}
</script>
