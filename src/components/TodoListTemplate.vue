<script>
export default {
  data() {
    return {
      todos: [
        {
          title: "Задача 1",
          isDone: false,
        },
        {
          title: "Задача 2",
          isDone: false,
        },
        {
          title: "Задача 3",
          isDone: false,
        },
        {
          title: "Задача 4",
          isDone: false,
        },
      ],

      newTask: ``,
      isImportant: false,
      priority: ``
    };
  },

  methods: {
    toggle(todo) {
      todo.isDone = !todo.isDone;
    },
    

    add() {
      if (!this.newTask) {
        return;
      }
      
      if (this.isImportant){
        this.todos.unshift({ title: this.newTask, isDone: false })
      } else if (this.priority && this.priority > 0) {
        this.todos.splice(this.priority - 1, 0, { title: this.newTask, isDone: false })
      } else {
        this.todos.push({ title: this.newTask, isDone: false })
      }
      this.newTask = ``
    },

    remove(index) {
      this.todos.splice(index, 1);
    },

    removeFirst() {
      this.todos.shift();
    },

    removeLast() {
      this.todos.pop();
    }
  },
};
</script>

<template>
  <div class="todo-list">
    <div class="input-group mb-3">
      <input type="text" class="form-control" v-model="newTask" />
      <button class="btn btn-outline-secondary" type="button" @click="add">
        Добавить
      </button>
    </div>
    <div class="row mb-3 ms-1">
      <div class="form-check mb-3 col-auto">
        <input class="form-check-input" type="checkbox" id="important" v-model="isImportant" />
        <label class="form-check-label" for="important">Важная задача</label>
      </div>
      <div class="col-auto">
        <label for="priority" class="form-label">Приоритет задачи</label>
        <input
          
          type="number"
          class="form-control"
          id="priority"
          style="width: 85px"
          placeholder="от 0"
          min="0"
          max="100",
          v-model="priority"
        />
      </div>
    </div>

    <div class="btn-group w-100 mb-3" role="group">
      <button
        class="btn btn-outline-secondary w-50"
        type="button"
        @click="removeFirst"
      >
        Удалить первую задачу
      </button>
      <button
        
        class="btn btn-outline-secondary w-50"
        type="button"
        @click="removeLast"
      >
        Удалить последнюю задачу
      </button> 
    </div>
    <ul class="list-group">
      <li v-for="(item, index) in todos" class="list-group-item" :class="{
        done: item.isDone,
      }">
        <div class="input-group">
          <div class="input-group-text">
            <input v-model="item.isDone" class="form-check-input mt-0" type="checkbox" />
          </div>
          <span class="input-group-text todo-title" @click="toggle(item)">
            {{ item.title }}
          </span>
          <button class="btn btn-outline-secondary" type="button" @click="remove(index)">
            X
          </button>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.todo-list {
  margin: 20px;
}

.todo-title {
  flex: 1;
}

.input-group {
  cursor: pointer;
}

.done .todo-title {
  text-decoration: line-through;
}
</style>
