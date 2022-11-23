<script>
/**
 *  props: ["title"]
 *  props: {
 *    title: String,
 *    count: Number,
 *  }
 */
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: {
      type: String,
      defaultValue: "Task Tracker",
      required: true,
    },
    showAddTask: {
      type: Boolean,
      defaultValue: false,
      required: true,
    },
  },
  emits: ["btn-click"],
  components: {
    Button,
  },
  computed: {
    homePage() {
      return this.$route.path === "/";
    },
  },
};
</script>

<template lang="">
  <header>
    <h2>
      {{ title }}
    </h2>
    <Button
      v-show="homePage"
      @btn-click="$emit('btn-click')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
