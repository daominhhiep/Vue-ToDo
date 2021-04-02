<template>
  <div>
    <form v-on:submit="addTodo">
        <input type="text"
               v-model="value"
               placeholder="Enter task..."/>
      <button>Add task</button>
    </form>
    <ul>
      <li v-for="(item, index) in lists"
          v-bind:item="item"
          v-bind:key="index">
        <span style="text-decoration: line-through"
                v-if="item.isDone===true">
            {{ item.text }}
        </span>
        <span v-else>{{ item.text }}</span>
        <button v-on:click="doneTodo(index)">v</button>
        <button v-on:click="removeTodo(index)">x</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ToDo",
  data() {
    return {
      value: "",
      lists: []
    }
  },
  methods: {
    addTodo: function (e) {
      e.preventDefault()
      if (this.value !== '') {
        this.lists.push({text: this.value, isDone: false})
        this.value = ''
      }
    },
    removeTodo: function (index) {
      this.lists.splice(index, 1)
    },
    doneTodo: function (index) {
      this.lists[index].isDone = !this.lists[index].isDone
    }
  },
}

</script>

<style scoped>

</style>
