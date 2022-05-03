<template>
  <p>Reaction Time - {{ score }}ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 100) {
      this.rank = "Bot";
    } else if (this.score < 250) {
      this.rank = "Ninja Fingers";
    } else if (this.score < 400) {
      this.rank = " Meh";
    } else {
      this.rank = "you suq";
    }
  },
};
</script>

<style>
.rank {
  color: rgb(0, 155, 75);
}
</style>
