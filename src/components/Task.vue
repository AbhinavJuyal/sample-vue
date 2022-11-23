<template lang="">
  <div
    :class="[{ reminder: task.reminder }, baseClass]"
    :key="task.id"
    @dblclick="$emit('toggle-reminder', task.id)"
  >
    <h4>
      <span>
        {{ task.text }}
      </span>
      <i class="fas fa-times" @click="$emit('delete-task', task.id)"></i>
    </h4>
    <h5>{{ task.day }}</h5>
  </div>
</template>
<script>
/**
 * emits: {
 *    emitName(payload) {
 *      // emitter function definition here
 *    }
 * }
 */
export default {
  name: "Task",
  data() {
    return {
      reminder: "reminder",
      baseClass: "task",
    };
  },
  props: {
    task: {
      type: Object,
      required: true,
    },
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
<style scoped>
.fas {
  color: red;
}

.task {
  text-align: left;
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task h4 {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.task.reminder {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
