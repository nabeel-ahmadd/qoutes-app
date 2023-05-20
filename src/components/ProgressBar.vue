<template>
  <div
    class="w-10/12 sm:w-8/12 border-2 text-center p-1 border-orange-700 rounded-2xl mx-auto">
    <div
      class="instagram rounded-xl transition-all duration-200"
      :style="{ width: calculateWidth + '%' }">
      {{ qoutes.length + "/" + toAdded }}
    </div>
  </div>
</template>

<script>
export default {
  inject: ["toAdded", "qoutes"],
  computed: {
    calculateWidth() {
      let width = (this.qoutes.length / this.toAdded) * 100;
      if (width > 100) {
        return 100;
      } else {
        return width;
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
