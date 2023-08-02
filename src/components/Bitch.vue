<template>
  <h1>bye {{ bitch }}</h1>
  <button @click="change">Bitch</button>
</template>

<script>
export default {
  name: "BitchFuck",
  data() {
    return { bitch: "bitch" };
  },
  methods: {
    change() {
      this.bitch = this.bitch === "bitch" ? "fuck" : "bitch";
    },
  },
};
</script>

<style scoped>
h1 {
  color: aquamarine;
}
</style>
