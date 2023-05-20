<template>
  <ul
    class="mx-auto w-11/12 md:w-7/12 grid grid-row-10 grid-cols-1 sm:grid-cols-2 mt-2 gap-2 lg:grid-row-auto lg:grid-cols-3">
    <!-- <li
      v-for="(qoute, index) in qoutes"
      @click="removeQoute(index)"
      :key="qoute.id"
      :index="qoute.index"
      class="list border-2 border-gray-500 pl-5 md:px-1 rounded-md transition-all duration-100">
      {{ qoute }}
    </li> -->
    <the-qoute
      @delete-qoute="removeQoute(index)"
      v-for="(qoute, index) in qoutes"
      :key="qoute.index"
      :qoute="qoute"
      :index="qoute.index"></the-qoute>
  </ul>
</template>

<script>
import TheQoute from "./TheQoute.vue";
export default {
  components: {
    TheQoute,
  },
  methods: {
    removeQoute(index) {
      this.qoutes.splice(index, 1);

      // console.log("deleted");
    },
  },
  inject: ["qoutes"],
};
</script>
