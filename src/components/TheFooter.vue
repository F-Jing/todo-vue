<template>
  <footer class="footer">
    <span class="todo-count">
      <strong>{{todosCount}}</strong> todo
    </span>
    <ul class="filters">
      <li>
        <!-- <a href="#/all" :class="{selected: filter === 'all'}" @click="handleChangeFilter('all')">All</a> -->
        <router-link to="/all" :class="{selected: filter === 'all'}">All</router-link>
      </li>
      <li>
        <!-- <a
          href="#/active"
          :class="{selected: filter === 'active'}"
          @click="handleChangeFilter('active')"
        >Active</a> -->
        <router-link to="/active" :class="{select: filter === 'active'}">Active</router-link>
      </li>
      <li>
        <!-- <a
          href="#/completed"
          :class="{selected: filter === 'completed'}"
          @click="handleChangeFilter('completed')"
        >Completed</a> -->
        <router-link to="/completed" :class="{select: filter === 'completed'}">Completed</router-link>
      </li>
    </ul>
    <button
      class="clear-completed"
      v-show="hasCompleted"
      @click="handleRemoveAllCompletedTodo"
    >Clear completed</button>
  </footer>
</template>
<script>
export default {
  name: 'TheFooter',
  created () {
    this.fetchFilter()
  },
  watch: {
    $route: 'fetchFilter'
  },
  // props: {
  //   todos: {
  //     type: Array,
  //     default: () => []
  //   },
  //   filter: {
  //     type: String,
  //     default: 'all'
  //   }
  // },
  computed: {
    filter () {
      return this.$store.state.filter
    },
    todosCount () {
      return this.$store.getters.todosCount
    },
    hasCompleted () {
      // return this.todos.some(data => data.completed)
      return this.$store.getters.hasCompleted
    }
  },
  methods: {
    // handleChangeFilter: function (filter) {
    //   this.$emit('update:filter', filter)
    // },
    handleRemoveAllCompletedTodo: function () {
      // let todos = [...this.todos]
      // todos = todos.filter(data => !data.completed)
      // this.$emit('update:todos', todos)
      this.$store.commit('removeCompleted')
    },
    fetchFilter: function () {
      const filter = this.$route.params.filter
      this.$store.commit('changeFilter', filter)
    }
  }
}
</script>
