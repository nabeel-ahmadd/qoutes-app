<template>
  <li
    @click="removeQoute(index)"
    class="list border-2 border-gray-500 pl-5 text-xl md:text-2xl font md:px-1 rounded-md transition-all duration-100">
    {{ qoute }}
  </li>
</template>
<script>
export default {
  props: ["qoute"],
  methods: {
    removeQoute(index) {
      this.$emit("delete-qoute", index);
    },
  },
};
</script>

<style scoped>
li {
  font-family: Fasthand;
  color: #6e6e6e;
}
li:hover {
  background-color: #ffe2e2;
  cursor: pointer;
}
</style>
