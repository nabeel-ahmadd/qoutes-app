<template>
  <the-header></the-header>
  <progress-bar></progress-bar>
  <add-qoute></add-qoute>
  <stored-qoutes></stored-qoutes>
</template>

<script>
import TheHeader from "./components/TheHeader..vue";
import ProgressBar from "./components/ProgressBar.vue";
import AddQoute from "./components/AddQoute.vue";
import StoredQoutes from "./components/StoredQoutes.vue";
export default {
  components: {
    TheHeader,
    ProgressBar,
    AddQoute,
    StoredQoutes,
  },
  data() {
    return {
      qoutesToAdd: 10,
      qoutes: [
        `Don't stop until you're proud.`,
        `Stay Peaceful.`,
        `Be the change that you wish to see in the others.`,
        `You are enogh just as you are.`,
        `Not all positive changes feel positive in the beginning.`,
        `The best is yet to be.`,
        `Stay positive`,
        `Think positive an positive things will happen.`,
      ],
    };
  },
  // methods: {
  //   removeQoute(index) {
  //     this.qoutes.splice(index, 1);
  //     console.log("deleted");
  //   },
  // },

  provide() {
    return {
      toAdded: this.qoutesToAdd,
      qoutes: this.qoutes,
    };
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Alkatra&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Fasthand&display=swap");
</style>
