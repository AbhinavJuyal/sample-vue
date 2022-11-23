<template lang="">
  <div>
    <Task
      :key="task.id"
      v-for="task in tasks"
      :task="task"
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
    />
  </div>
</template>
<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: {
      required: true,
      type: Array,
    },
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
<style lang=""></style>
