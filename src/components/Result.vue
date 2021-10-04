<template>
  <div class="result">
    <div class="title">{{ results[resultIndex].title }}</div>
    <div class="desc">{{ results[resultIndex].desc }}</div>
  </div>
</template>

<script>
export default {
  props: ["results", "totalCorrect"],
  computed: {
    resultIndex() {
      let index = 0;
      this.results.forEach((e, i) => {
        // checking if the total member of correct answers is above the minimum and below the maximum
        if (e.min <= this.totalCorrect && e.max >= this.totalCorrect) {
          // current index
          index = i;
        }
      });
      return index;
    },
  },
};
</script>
