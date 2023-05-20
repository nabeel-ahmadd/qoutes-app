<template>
  <form
    @submit.prevent="submitForm"
    class="flex justify-between mt-2 md:my-7 w-10/12 sm:w-6/12 md:9/12 mx-auto">
    <div class="w-6/12">
      <input
        type="text"
        v-model="newQoute"
        class="px-2 outline-none border-2 border-gray-400 rounded-md"
        placeholder="Enter Qoute" />
      <p v-if="inputIsInvalid" class="text-sm text-red-700">
        Please write something
      </p>
      <p v-if="arrayFull" class="text-sm text-red-700">
        Too many Qoutes! Delete some before adding new ones.
      </p>
    </div>
    <button
      class="instagram rounded-2xl text-center w-4/12 md:w-3/12 py-1 text-white font-semibold">
      Add Qoute
    </button>
  </form>
</template>

<script>
export default {
  inject: ["qoutes", "toAdded"],
  data() {
    return {
      newQoute: "",
      inputIsInvalid: false,
      arrayFull: false,
    };
  },
  methods: {
    submitForm() {
      if (this.qoutes.length >= this.toAdded) {
        this.arrayFull = true;
        this.inputIsInvalid = false;
      } else if (this.newQoute.trim() === "") {
        this.inputIsInvalid = true;
      } else {
        this.qoutes.push(this.newQoute);
        console.log(this.newQoute);
        this.newQoute = "";
        this.inputIsInvalid = false;
        this.arrayFull = false;
      }
    },
  },
};
</script>
<style scoped>
.instagram {
  background: #f09433;
  background: -moz-linear-gradient(
    45deg,
    #f09433 0%,
    #e6683c 25%,
    #dc2743 50%,
    #cc2366 75%,
    #bc1888 100%
  );
  background: -webkit-linear-gradient(
    45deg,
    #f09433 0%,
    #e6683c 25%,
    #dc2743 50%,
    #cc2366 75%,
    #bc1888 100%
  );
  background: linear-gradient(
    45deg,
    #f09433 0%,
    #e6683c 25%,
    #dc2743 50%,
    #cc2366 75%,
    #bc1888 100%
  );
  color: #fff;
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#f09433', endColorstr='#bc1888',GradientType=1 );
}
</style>
