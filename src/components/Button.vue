<template lang="">
  <button @click="onClick()" class="btn" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
  },
  emits: ["btn-click"],
  methods: {
    onClick() {
      this.$emit("btn-click");
    },
  },
};
</script>
<style lang=""></style>
