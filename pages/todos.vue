<template>
  <ul>
    <li v-for="(todo, index) in todos" :key="index">
      <input type="checkbox" :checked="todo.done" @change="toggle(todo)">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
    </li>
    <li><input placeholder="What needs to be done?" @keyup.enter="addTodo"></li>
  </ul>
</template>

<script>
  import { mapMutations } from 'vuex'
  import axios from 'axios'
  export default {
    data() {
      return {
        a: null
      }
    },
    async fetch ({ store, params }) {
      // let { data } = await axios.get('https://api.github.com')
      store.commit('todos/add','asda')
    },
    async asyncData(context) {
      console.log(context)
    },
    computed: {
      todos () { return this.$store.state.todos.list }
    },
    methods: {
      addTodo (e) {
        this.$store.commit('todos/add', e.target.value)
        e.target.value = ''
      },
      ...mapMutations({
        toggle: 'todos/toggle'
      })
    }
  }
</script>

<style>
  .done {
    text-decoration: line-through;
  }
</style>
