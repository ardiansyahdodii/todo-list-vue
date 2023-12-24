<template>
  <div class="flex flex-col justify-center items-center">
    <div>
      ToDo-List APP
    </div>
    <div>
      <InputComponent @taskAdded="addTask" />
    </div>
    <div>
     {{ tasks.filter(task => task.completed).length }}  from {{ tasks.length }} lists complete
    </div>
    <div>
      _______________________
    </div>
    <div>
      <div v-for="(task, index) in tasks" :key="task.index">
        <input type="checkbox" v-model="task.completed" />
        {{ task.text }}
        <button @click="removeTask(index)">(X)</button>
      </div>
    </div>
  </div>
</template>

<script>
import InputComponent from './components/InputForm.vue';

export default {
  components: {
    InputComponent
  },
  data() {
    return {
      tasks: [],
    }
  },
  methods: {
    addTask(task) {
      if (!task) return alert('Please enter a task')
      this.tasks.push({ text: task, completed: false })
    },
    removeTask(index) {
      this.tasks.splice(index, 1)
    },

  }
}
</script>